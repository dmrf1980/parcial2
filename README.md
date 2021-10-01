# Django - Boilerplate para empezar proyectos nuevos

Ejecutar:
```docker-compose up```

Para usar tienen que tener instalado  docker y docker-compose,

Dentro de la maquina de Python 3.8, se instala el django de la siguiente manera
```
pip install -r requirements.txt 
python manage.py migrate
python manage.py runserver

```
Las credenciales y nombre de la base de datos se tienen que definir previamenteaen el archivo DockerFile 


```
 environment:
      - MYSQL_ROOT_PASSWORD=root1234
      - MYSQL_DATABASE=base

```
La maquina de MySQL se utiliza con datos persistentes tambien dentro del DockerFile, con la ruta hacia la base de datos local. 

```
    volumes:
      - ./mysql:/var/lib/mysql

```

Tambien tienen que tener bajo el mysql local, utilizando el comando: 

```
	systemctl stop mysql
```

Para cargar la configuración de la conexion de proyecto con la base de datos tienen crear el archivo ./proyecto/local_settings, tiene uno de ejemplo ./proyecto/local_settings.php


```
cd ta2-django/proyecto
cp local_settings.py.ejemplo local_settings.py

```
