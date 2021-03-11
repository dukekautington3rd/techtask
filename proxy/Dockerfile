FROM nginx
ARG user
ARG pass

# auto generate a self signed cert

RUN openssl req -new -newkey rsa:4096 -sha256 -days 365 -nodes -x509 \
-subj "/C=US/ST=Confusion/L=Springfield/O=Dis/CN=techtask.io" \
-keyout /etc/nginx/server.key  -out /etc/nginx/server.cert 

RUN /bin/bash -c 'echo "$user:"`openssl passwd -apr1 -stdin<<<"$pass"` > /etc/nginx/.htpasswd'

COPY nginx.conf /etc/nginx/nginx.conf
#Uncomment to add your own password file
#COPY htpasswd /etc/nginx/.htpasswd 	

