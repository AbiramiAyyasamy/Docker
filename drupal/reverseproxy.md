server {
listen :80;
server_name abi.com;

location / {
  proxy_pass http://localhost:82;
  }
  }
