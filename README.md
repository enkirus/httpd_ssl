# httpd_ssl

Here we will use this file to enable ssl on aws EC2 at instance level for better protection. The certs are generated for example.com

Steps to generate your own seld-signed certs
- Make sure you have ssl installed
- openssl genrsa 1024 > localhost.key
- openssl req -new -key ./localhost.key  > localhost.csr (Here you can provide relevant details and in common name you can instance IP if you want or domain name)
- openssl x509 -in localhost.csr  -out localhost.crt -req -signkey localhost.key  -days 365
 you will have to move the certs to the path mentioned in ssl.conf which is in /etc/httpd/conf.d 

