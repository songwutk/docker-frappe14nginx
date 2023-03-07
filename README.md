# docker-frappe14nginx

Single Production Mode modify from https://github.com/frappe/frappe_docker/blob/main/pwd.yml


#Step by step

1) start docker
```
sudo docker-compose up -d
```
please wait about 5 minutes after all container run
``` 
sudo docker-compose ps 
```

Two containers should run one time and finish jobs by Exit status

![dockercomposeps](https://github.com/songwutk/docker-frappe14nginx/blob/main/doc/dps.jpg?raw=true) 



The others docker should up status.

2) Try to login administrator
   ```
    http://(yourhost):8090/
   ```

**username : administrator**  
**password : admin**

3) Follow step to complete site setup.
4) You can access mariadb from dbeaver or navicat by port 4306 to your host.

**username : root**  
**password : admin**

please rename username to your long secret name.
