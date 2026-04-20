## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
<img width="831" height="113" alt="image" src="https://github.com/user-attachments/assets/0383fdd9-aef7-4a12-92e6-8788df51bb3f" />


### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
<img width="1919" height="531" alt="image" src="https://github.com/user-attachments/assets/d9f1ac8f-64e3-4154-8be7-8168ed72f869" />

docker run -d --name mysql-wp --network net-wp \
-e MYSQL_ROOT_PASSWORD=1234 \
-e MYSQL_DATABASE=wordpress \
-e MYSQL_USER=wpuser \
-e MYSQL_PASSWORD=wp1234 \
mysql:8


### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
<img width="1902" height="788" alt="image" src="https://github.com/user-attachments/assets/480be13e-bb2b-4749-bdd7-72a051764669" />

docker run -d --name wordpress-wp --network net-wp -e WORDPRESS_DB_HOST=mysql-wp:3306 -e WORDPRESS_DB_USER=wpuser -e WORDPRESS_DB_PASSWORD=wp1234 -e WORDPRESS_DB_NAME=wordpress -p 9300:80 wordpress

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es 9300

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN

<img width="1034" height="949" alt="image" src="https://github.com/user-attachments/assets/4ac59dc2-17ef-4379-b997-c05f432aedbe" />

<img width="1287" height="670" alt="image" src="https://github.com/user-attachments/assets/10a27113-7f74-408b-adc7-6d89d7b79b32" />


Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.
<img width="1910" height="1088" alt="image" src="https://github.com/user-attachments/assets/d84220ca-08f4-48bd-8f19-7628be00a0cd" />

### Eliminar el contenedor wordpress
<img width="570" height="87" alt="image" src="https://github.com/user-attachments/assets/99067254-ecaa-4edc-afef-a015b5642b60" />


### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
# COMPLETAR

