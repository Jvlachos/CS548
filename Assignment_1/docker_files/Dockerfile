FROM nginx:latest

RUN	apt-get update && apt-get install -y git && \
	apt-get install -y make && \
	git clone  https://github.com/chazapis/hy548.git
	
RUN 	cd hy548 && \
	apt-get install -y hugo &&\
	git submodule init && \
	git submodule update && \
	make all && \
	cp -a html/public/. ../usr/share/nginx/html/ 
RUN     rm -rf /var/lib/apt/lists/*	
