1. **kubectl apply -f** nginx.yaml <br>
**kubectl port-forward** mynginx 8080:80 <br>
**kubectl logs** mynginx <br>
**kubectl exec -it** mynginx – /bin/sh <br>
**kubectl cp** mynginx:/usr/share/nginx/html/index.html index.html <br>
**kubectl cp** index.html mynginx:/usr/share/nginx/html/index.html <br>
**kubectl port-forward** mynginx 8080:80 <br>
**kubectl delete pod** mynginx <br>

2. **kubectl describe job** website-548 <br> 
3. **kubectl apply -f** nginx_server.yaml <br>
   **kubectl port-forward** mynginx 8080:80 <br>
   Both the nginx pod and the job pod use a specific folder in my local file system as a persistent volume.Through the persistent volume claim the two containers can communicate data.In this specific situation the job container places the index.html, which is the result of the website build process , inside the mounted volume.Then,the server container mounts it to /usr/share/nginx/html in order to serve it.
