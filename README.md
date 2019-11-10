# trucos-dockers
Trucos de Dockers

# Instalar Dockers
´´´
apt-get update && apt-get upgrade -y
apt  install docker.io
´´´

# Odoo
´´´
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
´´´
