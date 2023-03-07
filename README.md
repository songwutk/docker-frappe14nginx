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

docker-frappe14nginx_configurator_1     bash -c ls -1 apps > sites ...   **Exit 0**  
docker-frappe14nginx_create-site_1      bash -c wait-for-it -t 120 ...   **Exit 1**  
docker-frappe14nginx_queue-default_1    bench worker --queue default     Up  
docker-frappe14nginx_queue-long_1       bench worker --queue long        Up  
docker-frappe14nginx_queue-short_1      bench worker --queue short       Up  
docker-frappe14nginx_redis-cache_1      docker-entrypoint.sh redis ...   Up             6379/tcp  
docker-frappe14nginx_redis-queue_1      docker-entrypoint.sh redis ...   Up             6379/tcp  
docker-frappe14nginx_redis-socketio_1   docker-entrypoint.sh redis ...   Up             6379/tcp  
docker-frappe14nginx_scheduler_1        bench schedule                   Up  
docker-frappe14nginx_websocket_1        node /home/frappe/frappe-b ...   Up  
fbackend                                /home/frappe/frappe-bench/ ...   Up  
fmariadb                                docker-entrypoint.sh --cha ...   Up (healthy)   0.0.0.0:4306->3306/tcp,:::4306->3306/tcp  
nginx_frontend                          nginx-entrypoint.sh              Up             0.0.0.0:8090->8080/tcp,:::8090->8080/tcp  



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
