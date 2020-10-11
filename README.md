# djangular

## Set up project

Generate public key and add to Github
ssh-keygen
cat ~/.ssh/id_rsa.pub

Init git and push changes
git config --global user.email {mail}
git config --global user.name {name}
git push

Create virtual environment for Python
python3 -m venv .py

Enable and disable virtual python
source ./.py/bin/activate
deactivate

Install Django
pip install django
pip install djangorestframework

Install Sqlite
sudo apt-get install sqlite3

Prepare DB
python manage.py makemigrations
python mangae.py migrate

View DB
- sudo apt install sqlite3
sqlite3 db.sqlite3
sqlite> .tables
- GUI tool
sudo apt-get install sqlitebrowser
- pyCharm plugin 'Database Navigator'
menu DB Navigator / Database Browser / New Connection / SQLite

Run web server
python manage.py runserver

Download and install pyCharm on Raspberry Pi 4
sudo tar -xzf pycharm-community-2020.2.3.tar.gz -C /opt
cd /opt/pycharm-community-2020.2.3/bin
sudo ./pycharm.sh
sudo apt install default-jdk


