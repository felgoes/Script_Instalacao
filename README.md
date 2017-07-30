# Script_Instalacao

Se houver erro LOCALE:

export LC_ALL="en_US.UTF-8"
export LC_CTYPE="en_US.UTF-8"
sudo dpkg-reconfigure locales


Instalar Postgres / Criar Usuário:

sudo apt-get update
sudo apt-get install postgresql
sudo su postgres
psql
alter user postgres with password '123';
create user odoo with password '123' nosuperuser inherit createdb createrole replication;
\q
exit


Instalar Dependências:

wget https://raw.githubusercontent.com/Trust-Code/Tutorial-Instalacao/master/apt-requirements
wget https://raw.githubusercontent.com/Trust-Code/Tutorial-Instalacao/master/pip-requirements
sudo apt-get install -y --no-install-recommends $(grep -v '^#' apt-requirements)
sudo pip install --upgrade pip
sudo apt-get install python-setuptools
sudo pip install -r pip-requirements
sudo npm install -g less
sudo ln -s /usr/bin/nodejs /usr/bin/node
sudo apt-get install wkhtmltopdf 


Baixar Código do Odoo:

sudo git clone --depth 1 --branch 10.0 https://github.com/odoo/odoo.git


Iniciar o Odoo:

cd odoo
wget https://raw.githubusercontent.com/Trust-Code/Tutorial-Instalacao/master/odoo-config
./odoo-bin --config=odoo-config
000.000.0.0:8069
