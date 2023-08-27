Una parte importante para evitar errores sera validar los datos de entrada:

## ¿Qué es la validación de datos?
Se conoce como validación de datos al proceso que consigue evitar la introducción de datos incorrectos en una base de datos. Para ello, restringe el tipo de información que se puede introducir dentro de las celdas. Además, permite proveer instrucciones al usuario sobre cómo introducir la información.

Se trata, por tanto, del proceso que asegura que un programa como puede ser Excel, funcione con datos correctos, útiles y limpios. Esto se consigue mediante las conocidas como “reglas de validación”, “restricciones de validación” o “rutinas de comprobación”.

Para hacer estas comprobaciones de entradas podemos utilizar las sentencias IF/ELSE en la siguiente parte de codigo usamos solo la sentencia IF pero es un buen ejemplo en C#
Lo que hacen estos IF es comprobar que se ingresen datos y que estos sean enteros y positivos.

```private void button_genera_Click(object sender, EventArgs e)
        {
            if (numero_procesos.Text == "") //Si el campo es vacío el botón no debe realizar nada para evitar errores
            {
                MessageBox.Show("Ingrese un numero mayor a 0");
                return;
            }

            float procesos; //Para luego comrpobar si es negativo o no
            bool isNumber = float.TryParse(numero_procesos.Text, out procesos); //un booleano para comprobar que sea un numero

            if (!isNumber) //No se pueden ingresar letras
            {
                MessageBox.Show("Procesos debe contener un numero");
            }
            if (procesos <= 0)//No pueden ingresarse números negativos
            {
                MessageBox.Show("Procesos debe ser mayor a 0");
                numero_procesos.Text = "";
                return;
            }

            MessageBox.Show("Valor correcto"); //Indica que no ha habido ningún problema
            
            int numProcesos = (int)procesos; //Numero de procesos en enteros
            generarDatos(numProcesos); //Vamos a crear los datos de los lotes y procesos
        }
```

      
Una estructura muy comun para lo que seria un Try-Catch esta estructura nos permite manejar de una mejor manera las excepciones, veremos como es su implimentacion en Python.

El trybloque le permite probar un bloque de código en busca de errores.

El exceptbloque le permite manejar el error.

El elsebloque te permite ejecutar código cuando no hay ningún error.

El finallybloque le permite ejecutar código, independientemente del resultado de los bloques try y except.

### try
Cuando ocurre un error, o una excepción como la llamamos, Python normalmente se detendrá y generará un mensaje de error.

Estas excepciones ses pueden manejar usando la trydeclaración:

```El trybloque generará una excepción porque xno está definido:

        try:
          print(x)
        except:
          print("An exception occurred")
```
### Else
Puede utilizar la elsepalabra clave para definir un bloque de código que se ejecutará si no se generaron errores:
```En este ejemplo, el try bloque no genera ningún error:

        try:
          print("Hello")
        except:
          print("Something went wrong")
        else:
          print("Nothing went wrong")
```
### Finally 
El finallybloque, si se especifica, se ejecutará independientemente de si el bloque try genera un error o no.
```
        try:
          print(x)
        except:
          print("Something went wrong")
        finally:
          print("The 'try except' is finished")
```

Varias empresas y proyectos han desarrollado sistemas para manejar errores en programación. Algunos ejemplos notables incluyen:

### Sentry : 
Sentry es una plataforma de monitoreo de errores en tiempo real que permite a los desarrolladores rastrear, registrar y solucionar problemas en aplicaciones web y móviles. Ofrece seguimiento de errores, información contextual y notificaciones en tiempo real.

###  New Relic : 
New Relic es una plataforma de monitoreo y rendimiento de aplicaciones que ayuda a los equipos de desarrollo a identificar y resolver problemas de rendimiento y errores en aplicaciones web y móviles.

### Bugsnag : 
Bugsnag es otra herramienta de monitoreo de errores que ayuda a los desarrolladores a detectar y diagnosticar problemas en aplicaciones en tiempo real. Proporciona información detallada sobre los errores, incluyendo trazas de pila y contexto.

### Rollbar : 
Rollbar es una plataforma de detección y resolución de errores que ayuda a los equipos de desarrollo a identificar y solucionar problemas en aplicaciones web y móviles. Ofrece seguimiento de errores en tiempo real y herramientas de colaboración.

### Raygun : 
Raygun es una herramienta de monitoreo de aplicaciones que rastrea y notifica sobre errores y problemas en tiempo real. Proporciona información detallada sobre los errores y su impacto en los usuarios.

### Airbrake : 
Airbrake es una plataforma de seguimiento de errores que ayuda a los desarrolladores a detectar, diagnosticar y resolver problemas en aplicaciones web y móviles. Ofrece información sobre errores y permite a los equipos colaborar en la resolución de problemas.

### ELK Stack : 
ELK (Elasticsearch, Logstash, Kibana) es una combinación de herramientas utilizadas para la recopilación, búsqueda y visualización de datos de registro. Aunque no está diseñado exclusivamente para el manejo de errores, puede utilizarse para rastrear y analizar problemas en aplicaciones.

# Referencias
Ayuware. (2022). Validación de datos: qué es, en qué consiste y cómo se aplica. Blog de Ayuware.[ ](https://www.ayuware.es/blog/validacion-de-datos/)
