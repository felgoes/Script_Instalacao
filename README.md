# script_Instalacao
<table><tr><td>
<h4> Se houver erro LOCALE ao criar SSH: </h4>
 
export LC_ALL="en_US.UTF-8" <br/>
export LC_CTYPE="en_US.UTF-8" <br/>
sudo dpkg-reconfigure locales <br/>

</td></tr></table>

<h2> Instalar Postgres / Criar Usuário: </h2>

sudo apt-get update <br/>
sudo apt-get install postgresql <br/>
sudo su postgres <br/>
psql <br/>
alter user postgres with password '123'; <br/>
create user odoo with password '123' nosuperuser inherit createdb createrole replication; <br/>
\q <br/>
exit <br/>


<h2> Instalar Dependências: </h2>

wget https://raw.githubusercontent.com/Trust-Code/Tutorial-Instalacao/master/apt-requirements <br/>
wget https://raw.githubusercontent.com/Trust-Code/Tutorial-Instalacao/master/pip-requirements <br/>
sudo apt-get install -y --no-install-recommends $(grep -v '^#' apt-requirements) <br/>
sudo pip install --upgrade pip <br/>
sudo apt-get install python-setuptools <br/>
sudo pip install -r pip-requirements <br/>
sudo npm install -g less <br/>
sudo ln -s /usr/bin/nodejs /usr/bin/node <br/>
sudo apt-get install wkhtmltopdf  <br/>


<h2> Baixar Código do Odoo: </h2>

sudo git clone --depth 1 --branch 10.0 https://github.com/odoo/odoo.git <br/>


<h2> Iniciar o Odoo: </h2>

cd odoo <br/>
wget https://raw.githubusercontent.com/Trust-Code/Tutorial-Instalacao/master/odoo-config <br/>
./odoo-bin --config=odoo-config <br/>
000.000.0.0:8069 <br/>
