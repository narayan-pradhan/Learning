## Installing and Running Django on Raspberry pi4
### Hardware Specification
- Raspberry Pi 4 Model B Rev 1.4
### Os
- Ubuntu 22.04.1 LTS
### Installing and running ssh service
- sudo apt-get install ssh
- sudo systemctl start sshd.service

## Required packages
> install python3
> install pip : sudo apt-get install pip
> python3 -m pip install django- python3 -m django --version - sudo apt install python3-django
django-admin startproject mysite
python3 manage.py runserver
sudo pip install django-sslserver
vi mysite/settings.py
ALLOWED_HOSTS = [
        '192.168.1.24',
]
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'sslserver',
]
python3 manage.py runsslserver 0.0.0.0:8888
