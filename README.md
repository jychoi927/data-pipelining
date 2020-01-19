# data-pipelining
Data pipelining project



```
#000-default.conf
<VirtualHost *:8888>
       ServerName djangofordp
<Directory /home/cjy/projects/data-pipelining/dpproject/dpproject>
         <Files wsgi.py>
                Require all granted
         </Files>
</Directory>

<Directory /home/cjy/projects/data-pipelining/dpproject/pages>
	Require all granted
</Directory>

<Directory /home/cjy/projects/data-pipelining/dpproject/media>
	Require all granted
</Directory>

        WSGIDaemonProcess djangofordp python-path=/home/cjy/anaconda3/envs/venv37/lib/python3.7/site-packages
        WSGIProcessGroup djangofordp
        WSGIScriptAlias / /home/cjy/projects/data-pipelining/dpproject/dpproject/wsgi.py process-group=djangofordp
		Alias /static /home/cjy/projects/data-pipelining/dpproject/pages/static
		Alias /media /home/cjy/projects/data-pipelining/dpproject/media
</VirtualHost>
```



### current error



```
PermissionError at /upload/
[Errno 13] Permission denied: '/home/cjy/projects/data-pipelining/dpproject/media'

Request Method:	POST
Request URL:	http://192.168.0.144:8888/upload/
Django Version:	3.0.2
Exception Type:	PermissionError
Exception Value:	
[Errno 13] Permission denied: '/home/cjy/projects/data-pipelining/dpproject/media'
Exception Location:	/usr/lib/python3.6/os.py in makedirs, line 220
Python Executable:	/usr/bin/python3
Python Version:	3.6.8
Python Path:	
['/home/cjy/anaconda3/envs/venv37/lib/python3.7/site-packages',
 '/usr/lib/python36.zip',
 '/usr/lib/python3.6',
 '/usr/lib/python3.6/lib-dynload',
 '/usr/local/lib/python3.6/dist-packages',
 '/usr/lib/python3/dist-packages',
 '/home/cjy/projects/data-pipelining/dpproject']
Server time:	Sun, 19 Jan 2020 17:22:32 +0900
```

