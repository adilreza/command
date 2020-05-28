# command
> some important and frequently needed command.

## All About Python(Django) command

### How to collect static files (django rest, drf_yasg, and admin)
```
python3 manage.py collectstatic
```

## Server related and deployment to aws (setup nginx, postgres, supervisor)
### All about `Nginx`
```
    sudo apt install nginx
    sudo systemctl status nginx
    sudo systemctl restart nginx
    sudo systemctl stop/start nginx
```

### All About ** Supervisor **
> It makes sure that our application always run in the background. If anything wrong happend to the server, it automatically starts the process and make the application running always
```
    sudo apt install supervisor
    sudo systemctl status supervisor
    sudo systemctl restart supervisor
    sudo systemctl stop/start supervisor
```

Then go to `/etc/supervisor/conf.d` and create a gile _gunicorn.conf_ inside the file write the following line of code.
```
[program:gunicorn]
directory=/home/ubuntu/projectname
command=/home/ubuntu/env/bin/gunicorn --workers 3 --bind unix:/home/ubuntu/projectname/app.sock projectname.wsgi:application
autostart=true
autorestart=true
stderr_logfile=/var/log/gunicorn/gunicorn.err.log
stdout_logfile=/var/log/gunicorn/gunicorn.out.log
[group:guni]
programs:gunicorn
```

### Create Virtualenv

```
sudo apt-get install python3-venv
python3 -m venv env
source env/bin/activate 
```
###### here `env` is the name of virtual env

### How to install from *`requirments.txt`* file
```
pip3 install -r requorements.txt
```
