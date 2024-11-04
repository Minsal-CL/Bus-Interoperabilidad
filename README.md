# Manual de Instalación Laboratorio

## Archivos:
  * compose.yaml: Contenedores para habilitar el sistema.
  * CargaIc.xml: Canal para aceptar la carga de interconsultas desde un origen.
  * DerivacionChannel.xml: Canal de Mirth Connect para redirecionar interconsultas.
  * hapi.application.yaml: Archivo de configuraciones del Servidor Hapi.
  * Backup_Tei_core.backup: Backup de la base de datos con servicios terminológicos y guías de implementación.
  * TestingRed.postman_collection.json: Collection postman para probar la red.
  * Bundle_iniciar.fhir.json: Ejemplo de un recurso FHIR.

## Paso a Paso
 
 1. Verifcar que el contenedor: "tei_fhir" se encuentre comentado y mantenerlo así. Y que el depend_on del contenedor: "mirthconnect" no se encuentre habilitado el tei_fhir.

 2. Realizar el siguiente comando:
 
  ```
  docker compose up 
  ```

 Esperar que el contenedor de la base de datos postgres se encuentre activo.

 3. Restaurar el Backup de la base de dato, en el contenedor "postgres". Se recomienda pgAdmin para realizar el restore.

 4. Una vez restaurada la base de datos postgres. Detener contendores. Habilitar todo lo relacionado al contenedor "tei_fhir", luedo realizar nuevamente un:
 
 ```
  docker compose up 
 ```
 > [!IMPORTANT]
 > Bloquear o comentar puertos de la Base de Datos

 > [!TIP]
 > Mantener activo los puertos del servidor tei_fhir, para revisar instalación. Luego bloquearlos dado que no son requeridos para el sistema.

 5. Instalar canales en MirthConnect y realizar los ajustes necesarios.

 > [!IMPORTANT]
 > No se encuentra ningún destino habilitado, recomiendo generar un de ejemplo para que funcione el canal **DerivacionChannel.xml**

 > [!TIP]
 > Utilizar collection postman y ejemplo Bundle_iniciar.fhir.json para realizar pruebas





