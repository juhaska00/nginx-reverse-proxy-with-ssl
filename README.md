# nginx-reverse-proxy-with-ssl
Nginx reverse proxy with ssl self-signed certificate

1. create nginx.conf
2. openssl req -x509 -new -newkey rsa:2048 -keyout nginx-selfsigned.key -out nginx-selfsigned.crt -days 365 -nodes -config openssl.cnf
3. add this to parameter store
aws ssm put-parameter --name "/my-app/nginx/cert" --type "SecureString" --value file:// --overwrite
aws ssm get-parameters --names
4. add certs to root certificates
5. voila