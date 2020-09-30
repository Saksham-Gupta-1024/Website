# GreenClothaWay

## prerequisites
`python >= 3.6`

`pip3 lts`

`python-virtualenv`

## preperation
create a virtual environment and update pip and wheel
```
python3 -m venv <venvname>
source <venvname>/bin/activate
pip install -U pip
pip install -U wheel
```

## installation
install package. one can find the releases [here](https://github.com/GreenClothaWay/Blog/tree/master/release) 
```
pip install greenclothaway-<release_version>-py3-none-any.whl
```

## configuration
```
mv <venvname>/lib/python3.8/site-packages/website/settings.py.sample <venvname>/lib/python3.8/site-packages/website/settings.py
```

in this settings.py you now have to add a django secret key.
you can create a secret key by this python oneliner : 

```python -c 'from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())'```

for a development server any random 50-character long string will do.
Also if you want to use another database then the default (SQlite) you have to configure it here.

after that you will have to create a superuser and migrate django database stuff n all.

```
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser
```
the manage.py command will be available in your virtual environment after the installation.

now you're all set to turn on your testserver on localhost

```
manage.py runserver
```



if you want to run this application on a productive server, you'll have to set up a webserver and configure it according to django's how to.
but that's on you dude!
