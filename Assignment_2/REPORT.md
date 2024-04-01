# 1<br>
a.  **kubectl apply -f** nginx.yaml <br>
b.**kubectl port-forward** mynginx 8080:80 <br>
c.**kubectl logs** mynginx <br>
d.**kubectl exec -it** mynginx – /bin/sh <br>
![image](https://github.com/Jvlachos/CS548/blob/main/Assignment_2/images/1d.png) <br>
e.**kubectl cp** mynginx:/usr/share/nginx/html/index.html index.html <br>
**kubectl cp** index.html mynginx:/usr/share/nginx/html/index.html <br>
**kubectl port-forward** mynginx 8080:80 <br>
![image](https://github.com/Jvlachos/CS548/blob/main/Assignment_2/images/1e.png) <br>
f.**kubectl delete pod** mynginx <br>

# 2 
**kubectl describe job** website-548 <br>
![image](https://github.com/Jvlachos/CS548/blob/main/Assignment_2/images/2.png) <br>
# 3
**kubectl apply -f** nginx_server.yaml <br>
**kubectl port-forward** mynginx 8080:80 <br>
Both the nginx pod and the job pod use a specific folder in my local file system as a persistent volume.<br>Through the persistent volume claim the two containers can communicate data.In this specific situation<br>the job container places the index.html,which is the result of the website build process ,<br>inside the mounted volume.Then,the server container mounts it to /usr/share/nginx/html in order to serve it.<br>
![image](https://github.com/Jvlachos/CS548/blob/main/Assignment_2/images/3.png)<br>
# 4
![image](https://github.com/Jvlachos/CS548/blob/main/Assignment_2/images/4.png)
