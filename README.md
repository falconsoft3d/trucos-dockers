# Trucos y Herramientas de Dockers

# Instalar Dockers
```
apt-get update && apt-get upgrade -y
apt  install docker.io
```

# Listar Dockers
```
docker ps
```

# Entrar dentro del docker existente
```
docker exec -it CONTAINER_ID bash
```


# Instalar Portainer
```
docker pull portainer/portainer
docker run -d -p 9000:9000 -p 8000:8000 --name portainer --restart always -v /var/run/docker.sock:/var/run/docker.sock -v /path/on/host/data:/data portainer/portainer
```


# Odoo
```
docker pull odoo:13

cd /opt
mkdir /odoo
cd /odoo
mkdir /server
cd /server
mkdir /extra-addons
mkdir /opt/odoo/server/extra-addons
chown odoo: /opt/odoo/ -R

docker run -v /opt/odoo/server/extra-addons:/mnt/extra-addons -p 8069:8069 --name odoo --link db:db -t odoo
```

# Pgadmin4
```
docker pull dpage/pgadmin4
docker run -p 5050:80 --link db:db --name pgadmin4dev -e "PGADMIN_DEFAULT_EMAIL=mfalcon@ynext.cl"   -e "PGADMIN_DEFAULT_PASSWORD=secret" -d dpage/pgadmin4
```

# Run Ubuntu
```
docker run -ti ubuntu /bin/bash
```

# Creamos una copia de la imagen con una nueva etiqueta
```
docker image tag 775349758637 miubuntu:1.1
```

# Historial del Docker
```
docker image history f70b4e424946
```

# Correr un Docker y dejarlo funcionando
```
docker run -d nginx:1.15.7
```

# Parar Apache 2
```
sudo service apache2 stop
```
