# Building Restaurant Site Using Django 2.1.4 and MySQL

1. Create the database


	mysql> CREATE DATABASE django_restaurant;
	mysql> CREATE USER 'restaurant'@'localhost' IDENTIFIED BY 'restaurant';
	mysql> GRANT ALL PRIVILEGES ON django_restaurant.* TO 'restaurant'@'localhost';
	mysql> FLUSH PRIVILEGES;

	mysql> show grants for 'restaurant'@'localhost';                             
	+---------------------------------------------------------------------------+
	| Grants for restaurant@localhost                                           |
	+---------------------------------------------------------------------------+
	| GRANT USAGE ON *.* TO `restaurant`@`localhost`                            |
	| GRANT ALL PRIVILEGES ON `django_restaurant`.* TO `restaurant`@`localhost` |
	+---------------------------------------------------------------------------+

2. Create Django Project

	> django-admin startproject 'project_name'

3. Setting the database credentials

	DATABASES = {
    'default': {
        'ENGINE'	: 'django.db.backends.mysql',
        'NAME'		: 'django_restaurant',
        'USER'		: 'restaurant',
        'PASSWORD': 'restaurant',
        'HOST'		: 'localhost',
        'PORT'		: '3306',
    }
	}		

4. Run the server

	> python manage.py runserver	

5. Create superuser

	> python manage.py migrate

	> python manage.py createsuperuser
		