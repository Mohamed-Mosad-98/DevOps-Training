# Lab 12: Docker Volume & Bind Mount (Nginx)
Steps:
1) `docker volume create nginx_logs`
2) `docker run -d --name lab12-nginx -p 8080:80 -v nginx_logs:/var/log/nginx -v ~/nginx-bind/html:/usr/share/nginx/html:ro nginx:alpine`
3) `curl http://localhost:8080`
4) Edit `~/nginx-bind/html/index.html` and curl again
5) `docker exec -it lab12-nginx tail -n 20 /var/log/nginx/access.log`
6) `docker rm -f lab12-nginx && docker volume rm nginx_logs`
