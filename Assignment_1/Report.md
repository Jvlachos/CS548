#Assignment 1

1.
    a.docker pull nginx:1.23.3 , docker pull nginx:1.23.3-alpine
    b.docker images 
        nginx is 142MB while nginx-alpine is 40.7 MB
    
    c.docker run --name mynginx -p 80:80 -d  2bc7edbc3cf2 (image id)
      curl http://localhost : and we get the welcome to nginx       html       
    d.docker ps to display the running containers
    e.docker logs mynginx
    f.docker stop mynginx
    g.docker start mynginx
    h.docker stop mynginx && docker rm mynginx

2.
    a.docker exec -it mynginx sh
      cd /usr/share/nginx/html
      vi index.html
      curl http://localhost
    b.docker cp mynginx:usr/share/nginx/html/index.html index.html
      docker cp index.html mynginx:usr/share/nginx/html/index.html
      docker stop mynginx && docker rm mynginx
    c.The changes are not visible since a new container was created with the default configurations of the nginx server,as such,the index.html has the default contents.

3.
    -git clone https://github.com/chazapis/hy548.git
    the theme needs to be loaded:
    -git submodule init && git submodule update
    -make all
    -docker run --name mynginx -p 80:80 -d -v /home/dimitris/cs548/hy548/html/public:/usr/share/nginx/html 2bc7edbc3cf2
    

4.
    a.to build the image : docker build -t <directory containing the Dockerfile>
    b.docker tag mynginx:latest dvlachos/mynginx
      docker push dvlachos/mynginx

    c.My image is 1.08GB while the image that i based it on is 187MB .This is expected because i installed git,hugo and make .Other dependencies were also installed automatically from the packet manager making the image larger.
    
    d.I used the rm -rf /var/lib/apt/lists/* command insidethe docker file in order to clear the temporary files of the packet manager(apt).


