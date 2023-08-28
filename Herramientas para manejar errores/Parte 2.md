El siguiente es un fragmento de codigo de una pagina web desarollada en php.
Es un sistema que ayuda a un entrenador de Rugby a llevar el control de sus jugadores, con cuestionarios de bienestar
y registrar pruebas fisicas. El fragmento que mostrare es para validar las entradas de un formulario de registro:


![image](https://github.com/JaredRoC11/Tolerante-a-fallas/assets/106403018/966006fe-d5b8-4ac7-af07-bc88b43e71b8)


![image](https://github.com/JaredRoC11/Tolerante-a-fallas/assets/106403018/3639bd19-d90e-48ee-8b33-fd26d8a960fe)


Esta funcion nos ayuda a validar que los campos no esten vacios:

```function ValidarCampos() {
            var mensaje = "Faltan campos por llenar";
            var contra = ValidarContrasena();
            
            if (!contra) {
                alert(contraInvalida);
                return false; // Evitar el envío del formulario
            } else if (!registro.codigo.value || !registro.nombre.value || !registro.peso.value || !registro.altura.value
                || !registro.correo.value || !registro.password.value || !registro.anio_nac.value) {
                alert(mensaje);
                return false; // Evitar el envío del formulario
            } else {
                return true; // El formulario es válido, puede ser enviado
            }
        }
```
