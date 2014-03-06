SIDB
====

SIDB: Severs Infomation DB
Fork from http://johnsteven.blog.51cto.com/blog/2523007/1046880

### Need package
+ bison-2.5
+ mysql
+ nginx
+ Python-2.6.X
+ uwsgi-1.2.3
+ xlwt-0.7.4
+ MySQL-python-1.2.3
+ web.py-0.36

### Install step
+ install nginx & mysql
++ <pre><code>sudo apt-get install nginx mysql-server</code></pre>

+ install python module
++ <pre><code>sudo apt-get install python-webpy</code></pre>
++ <pre><code>sudo apt-get install python-mysqldb python-xlwt</code></pre>

+ init database
++ <pre><code>create database sidb;</code></pre>
++ <pre><code>grant all on sidb.* to sidb@127.0.0.1 identified by 'sidbpwd';</code></pre>
++ <pre><code>flush privileges;</code></pre>
++ <pre><code></code></pre>
++ <pre><code></code></pre>
