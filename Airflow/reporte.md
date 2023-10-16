### ¿Qué es Apache Airflow?
La plataforma Apache Airflow permite la creación, la planificación y el seguimiento de flujos de trabajo a través de la programación informática. Es una solución totalmente de código abierto, muy útil para la arquitectura y la orquestación de circuitos complejos de datos y para el lanzamiento de tareas.

Tiene varias ventajas. En primer lugar, es una plataforma dinámica, ya que todo lo que se puede hacer con el código Python, se puede hacer en Airflow.
En primer lugar para instalar Airflow en Windows necesitamos la ayuda de un subsistema de Linux lo cual se hace de la siguiente forma:
![image](https://github.com/JaredRoC11/Tolerante-a-fallas/assets/106403018/66d5159f-5a1b-46c8-8d78-6c5d9d4e4be6)

Buscamos la opción de “Activar o desactivar características de Windows” y habilitamos la opción de “Subsistemas de Windows para Linux”. 
Después de esto buscamos en la tienda de Windows una distribución de Linux que esté disponible yo en mi caso use Ubuntu.

Cuando abrimos este nos pedirá un usuario y contraseña, seguido de eso haremos uso de los siguientes comandos: 


```
# add-repository universe
  sudo apt-add-repository universe 
  
  # add-repository universe
  sudo apt-get update 
  
  # revision version python
  python3 --version
  
  # instalacion pip
  sudo apt-get install python3-pip 
  
  # exportar variable
  export SLUGIFY_USES_TEXT_UNIDECODE=yes 
  
  # instalacion sql alquemy compatible con airflow 2.20
  sudo pip install SQLAlchemy==1.3.24
  
  # instalacion airflow 
  sudo pip install apache-airflow 
  
  # revision version airflow
  airflow version
  
  # inicializacion de la base de datos
  airflow db init
  
  # creacion del usuario para login
  airflow users  create --role Admin --username username1 --email user@email.com --firstname user --lastname name --password contraseña
```

En el ultimo comando tenemos que crear cada dato para despues entrar a Airflow

```
# iniciar el servicio de airflow
airflow webserver -p 7890
```
Ini
