SIDB
====

SIDB: Servers Infomation DB

Fork from http://johnsteven.blog.51cto.com/blog/2523007/1046880

### Need package
+ mysql
+ nginx
+ Python-2.6+
+ uwsgi
+ xlwt
+ MySQL-python
+ web.py

### Bug Fix
```
uwsgi_config.xml add "<plugins>python</plugins>" in python 2.7
controls/control.py add "import sys
reload(sys)
sys.setdefaultencoding('utf8')" in python 2.7
```
### Install step
+ install nginx & mysql
```
sudo apt-get install nginx mysql-server
```

+ install python module
```
sudo apt-get install python-webpy
sudo apt-get install python-mysqldb python-xlwt uwsgi-core uwsgi-plugin-http
```

+ init database
```
create database sidb;
grant all on sidb.* to sidb@127.0.0.1 identified by 'sidbpwd';
flush privileges;
```
+ import database
```
mysql -h 127.0.0.1 -usidb -p sidb < yunwei.sql
```

+ config nginx
```
    server 
      { 
        listen       80; 
        server_name  127.0.0.1; 
        location / { 
            include uwsgi_params; 
            uwsgi_pass 127.0.0.1:9090; 
        } 
        location ^~ /static/ 
        { 
            alias   /home/timo/github/timoseven/SIDB/static/; 
        } 
      } 
```

+ config and start uwsgi
```
uwsgi -x uwsgi_config.xml
```
