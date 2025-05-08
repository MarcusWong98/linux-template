Setup ssl cert for nginx

1. Setup CA cert
   1a. Generate a private key for CA - openssl genrsa
   1b. Create a CSR(Certificate Signing Request) with CA private key - openssl req
   1c. Create a CA cert with the CA CSR - openssl x509

2. Setup a CSR for your host
   2a. Generate a private key - openssl genrsa
   2b. Create a CSR with the private key - openssl req

3. Setup required files and directories for CA
   3a. sudo touch /etc/pki/CA/index.txt
   3b. sudo mkdir /etc/pki/CA/newcerts
   3c. echo 00 | sudo tee /etc/pki/CA/serial

4. Create the intermedium cert with the CSR for your host - openssl x509
   **Remark: Might need to edit openssl.conf

5. Append following config entries to nginx.conf
   ssl_certificate [Your cert]
   ssl_certificate_key [Your key]
   **Remark: sudo pkill -f nginx
