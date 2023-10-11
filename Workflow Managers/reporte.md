Para este trabajo usaremos Python, sqlite3 y prefect.
Iniciaremos mostrando el código que fue tomado de referencia de un video, luego mostraremos lo que nos dio la ejecución de este. 

```
import requests
import json
from collections import namedtuple
from contextlib import closing
import sqlite3

from prefect import task, flow

## extract
@task
def get_complaint_data():
    r = requests.get("https://www.consumerfinance.gov/data-research/consumer-complaints/search/api/v1/", params={'size':10})
    response_json = json.loads(r.text)
    return response_json['hits']['hits']

## transform
@task
def parse_complaint_data(raw):
    complaints = []
    Complaint = namedtuple('Complaint', ['data_received', 'state', 'product', 'company', 'complaint_what_happened'])
    for row in raw:
        source = row.get('_source')
        this_complaint = Complaint(
            data_received=source.get('date_received'),
            state=source.get('state'),
            product=source.get('product'),
            company=source.get('company'),
            complaint_what_happened=source.get('complaint_what_happened')
        )
        complaints.append(this_complaint)
    return complaints

## load
@task
def store_complaints(parsed):
    create_script = 'CREATE TABLE IF NOT EXISTS complaint (timestamp TEXT, state TEXT, product TEXT, company TEXT, complaint_what_happened TEXT)'
    insert_cmd = "INSERT INTO complaint VALUES (?, ?, ?, ?, ?)"

    with closing(sqlite3.connect("cfpbcomplaints.db")) as conn:
        with closing(conn.cursor()) as cursor:
            cursor.executescript(create_script)
            cursor.executemany(insert_cmd, parsed)
            conn.commit()

@flow(name="my etl flow")
def my_etl_flow():
    raw = get_complaint_data()
    parsed = parse_complaint_data(raw)
    store_complaints(parsed)

my_etl_flow._run()
```
![image](https://github.com/JaredRoC11/Tolerante-a-fallas/assets/106403018/9ee640c2-bcc7-4154-8c52-9692889eee66)

•	A grandes rasgos el código cuando es ejecutado toma datos del link que se observa en el código, que en si es información de consumidores.
•	 Cuando esta información es obtenida la trasforma en datos un poco más legibles.
•	Y por último toda esta información trasformada es guardada en una base de datos SQLite
Aqui accedemos a la base de datos

![image](https://github.com/JaredRoC11/Tolerante-a-fallas/assets/106403018/bb196096-29a7-4be8-9263-ab2f78e7ca6e)
![image](https://github.com/JaredRoC11/Tolerante-a-fallas/assets/106403018/1d0d401a-23e4-4b93-947d-75d18a48a735)

