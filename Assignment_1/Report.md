Name : Dimitris Vlachos

AM:4492

**Assignment 1**

1.

a.**_docker pull nginx:1.23.3 , docker pull nginx:1.23.3-alpine_**

b.**_docker images_**

nginx is 142MB while nginx-alpine is 40.7 MB

c.-**_docker run --name mynginx -p 80:80 -d 2bc7edbc3cf2_** (image id)

\-**_curl <http://localhost>_** : and we get the welcome to nginx html


![image](https://github.com/Jvlachos/CS548/blob/main/Assignment_1/Images/1cd.png)

e.**_docker logs mynginx_**

f.**_docker stop mynginx_**

g.**_docker start mynginx_**

h.**_docker stop mynginx && docker rm mynginx_**

2.

a.-**_docker exec -it mynginx sh_**

**_\-cd /usr/share/nginx/html_**

**_\-vi index.html_**

**_\-curl_** [**_http://localhost_**](http://localhost)

![image](https://github.com/Jvlachos/CS548/blob/main/Assignment_1/Images/2a.png)

b.-**_docker cp mynginx:usr/share/nginx/html/index.html index.html_**

\-**_docker cp index.html mynginx:usr/share/nginx/html/index.html_**

**_\-docker stop mynginx && docker rm mynginx_**

c.The changes are not visible since a new container was created with the default configurations of the nginx server,as such,the index.html has the default contents.

3.

**_\-git clone <https://github.com/chazapis/hy548.git>_**

the theme needs to be loaded:

**_\-git submodule init && git submodule update_**

**_\-make all_**

**_\-docker run --name mynginx -p 80:80 -d -v /home/dimitris/cs548/hy548/html/public:/usr/share/nginx/html 2bc7edbc3cf2_**

![image](https://github.com/Jvlachos/CS548/blob/main/Assignment_1/Images/3.png)

4.

a.to build the image : **_docker build -t &lt;directory containing the Dockerfile&gt;_**

b.-**_docker tag mynginx:latest dvlachos/mynginx_**

**_\-docker push dvlachos/mynginx_**

![image](https://github.com/Jvlachos/CS548/blob/main/Assignment_1/Images/4b.png)

c.My image is 1.08GB while the image that i based it on is 187MB .This is expected because i installed git,hugo and make .Other dependencies were also installed automatically from the packet manager making the image larger.

d.I used the **_rm -rf /var/lib/apt/lists/\*_** command inside the docker file in order to clear the temporary files of the packet manager(apt).
