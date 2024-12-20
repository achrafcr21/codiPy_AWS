Configuración de AWS IoT
Ve a la sección de configuración de AWS IoT al inicio del archivo. Cambia estos campos:

ENDPOINT: Es el endpoint que te da AWS IoT cuando configuras tu dispositivo. Tiene un formato como xxxxx-ats.iot.us-east-1.amazonaws.com.
CLIENT_ID: Pon un identificador único para tu dispositivo. Por ejemplo: dispositivo_grupo2.
Certificados:
CERTIFICATE_PATH: Ruta al certificado del dispositivo, algo como certificados/certificate.pem.crt.
PRIVATE_KEY_PATH: Ruta a la clave privada del dispositivo, algo como certificados/private.pem.key.
CA_PATH: Ruta al certificado raíz de Amazon, algo como certificados/AmazonRootCA1.pem.
2. Configuración de la Base de Datos
Busca la sección donde se configura la base de datos. Necesitarás cambiar:

DB_HOST: Esto normalmente es localhost si usas tu propio ordenador, pero puede variar si tienes una base de datos en la nube.
DB_USER: El nombre del usuario de tu base de datos, por ejemplo: root.
DB_PASSWORD: La contraseña de tu base de datos.
DB_NAME: El nombre de la base de datos que estés usando. Por ejemplo: projecte_assistencia.
3. Tablas de la Base de Datos
Este código asume que tienes una tabla llamada usuarios con un campo uid y otra tabla llamada asistencias para registrar las entradas. Asegúrate de que tu base de datos tiene estas tablas con los nombres y columnas correctas:

usuarios:
id: Número único para cada usuario.
uid: El identificador RFID asociado al usuario.
asistencias:
id: Número único para cada asistencia.
usuario_id: Relación con el usuario.
fecha: Fecha de la asistencia.
hora_entrada: Hora de entrada.
estado: Estado de la asistencia (por ejemplo, presente).
4. Topics MQTT
Cambia los topics para que coincidan con los que estás usando en AWS IoT:

TOPIC: El topic al que se suscribe el dispositivo. Por ejemplo: rfid/uid.
RESPONSE_TOPIC: El topic donde el dispositivo envía confirmaciones. Por ejemplo: rfid/uid/response.