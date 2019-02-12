# Nginx
Installation, configuration and explanation of Nginx

## Installing from package
```
sudo apt-get install nginx
```
## Installing from source

installing from source allows you to add third-party libraries

1 - Download the source
```
wget https://nginx.org/download/nginx-1.12.1.tar.gz
```
2 - Decompress the source
```
tar -zxvf nginx-1.12.1.tar.gz 
cd nginx-1.12.1.tar.gz
```
3 - Update system and install tools
```
sudo apt-get update
sudo apt-get install build-essential
```

4 - Configure and compile

Simple configure and install
```
./configure
```
Configure installation path
```
./configure --prefix=/usr —conf-path=/etc/nginx
```
###### Note: Usually the daemons are in /usr/sbin, and the configuration files in /etc/

Configure and add modules

```
./configure --with-http_ssl_module \
--with-http_spdy_module \
--with-http_realip_module \
--with-http_stub_status_modul
```
When the compilation is finished it should end with a message indicating the nginx files

```
Configuration summary
  + using system PCRE library
  + OpenSSL library is not used
  + using system zlib library

  nginx path prefix: "/usr/local/nginx"
  nginx binary file: "/usr/local/nginx/sbin/nginx"
  nginx modules path: "/usr/local/nginx/modules"
  nginx configuration prefix: "/usr/local/nginx/conf"
  nginx configuration file: "/usr/local/nginx/conf/nginx.conf"
  nginx pid file: "/usr/local/nginx/logs/nginx.pid"
  nginx error log file: "/usr/local/nginx/logs/error.log"
  nginx http access log file: "/usr/local/nginx/logs/access.log"
  nginx http client request body temporary files: "client_body_temp"
  nginx http proxy temporary files: "proxy_temp"
  nginx http fastcgi temporary files: "fastcgi_temp"
  nginx http uwsgi temporary files: "uwsgi_temp"
  nginx http scgi temporary files: "scgi_temp"
```

5 - make and install (finish installation)
```
make
sudo make install
```
## Some nginx commands for nginx installing from source

- Check nginx version
```
/usr/local/nginx/sbin/nginx -v
  nginx version: nginx/1.12.1
```
- Check nginx configuration file
```
sudo /usr/local/nginx/sbin/nginx -t
  nginx: the configuration file /usr/local/nginx/conf/nginx.conf syntax is ok
  nginx: configuration file /usr/local/nginx/conf/nginx.conf test is successful
```
- Run nginx
```
sudo /usr/local/nginx/sbin/nginx
```
- Stop nginx
```
sudo /usr/local/nginx/sbin/nginx -s stop
```
- Check if nginx is running
```
ps aux |grep nginx
```

