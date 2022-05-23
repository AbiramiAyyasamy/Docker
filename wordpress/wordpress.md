server {
listen :80;
server_name mydrupal.com;

location / {
  proxy_pass http://localhost:82;
  }
  }
