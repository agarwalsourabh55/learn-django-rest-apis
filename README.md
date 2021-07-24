# learn-django-rest-apis
How to create REST APIs using Django: Talk delivered at Slack Community Jaipur

# Setting up Django and DRF on unix based OS

## Step-1: Install python3 pip and mysql server
```
sudo apt-get install python3-pip mysql-server
```

## Step-2: Install virtual env and MySQL
```
pip3 install virtualenv pymysql
```

## Step-3: Create a virtualenv
```
virtualenv -p python3 -v env
```

## Step-4: Activate virtualenv
```
. env/bin/activate
```

## Step-5: Create a Django project
```
django-admin startproject slackrestapis
```

## Step-6: Create a mysql database
```
mysql -u root -p
create database slackjaipur;
ALTER DATABASE slackjaipur CHARACTER SET 'utf8';
CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON slackjaipur.* TO 'user'@'localhost';
FLUSH PRIVILEGES;
exit
```

## Step-7: Update settings.py for our db

ENGINE: django.db.backends.mysql
NAME: 'slackjaipur'
USER: 'user'
PASSWORD: 'password'
HOST: '127.0.0.1'
PORT: '3306'

## Step-8: Run migrations
```
python manage.py makemigrations
python manage.py migrate
```

## Step-9: Install Django Rest Framework
```
pip install djangorestframework
```

## Step-10: Create an App
```
python manage.py startapp restapis
```

And add 'rest_framework' to your INSTALLED_APPS setting


## Step-11: Verify proper setup of project
```
python manage.py runserver
```


# Setting up Django and DRF project on Windows

Follow this short offical django tutotrial on [how to install Django on windows](https://docs.djangoproject.com/en/3.2/howto/windows/)

Now to setup a Django project follow [this tutorial](https://codesource.io/setting-up-a-virtual-environment-for-your-django-project/)

Follow Step-2 of [this tutorial](https://codefires.com/how-connect-mysql-database-django-using-mysqlclient-package/) to install and connect MySQL to Django on Windows

Then follow step-7 to step-11 in previous part


# Alternate: Setting up Django with MySQL can be a little bit tricky on windows if you are new. You can use this method instead :-

## Install [virtualbox](https://www.virtualbox.org/) on windows

## Install Ubuntu 20.04.2.0 LTS on it using [this iso image](https://ubuntu.com/download/desktop) 

## Follow [this tutorial](https://www.lifewire.com/install-ubuntu-linux-windows-10-steps-2202108/) on how to install Ubuntu on virtalbox


## After the installation is complete, run these commands in your terminal
```
sudo apt-get install update
sudo apt-get install upgrade
```

## Then follow step-1 to step-11 in above instructions

