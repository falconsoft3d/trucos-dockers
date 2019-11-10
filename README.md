# Trucos y Herramientas de Dockers

# Instalar Dockers
```
apt-get update && apt-get upgrade -y
apt  install docker.io
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

