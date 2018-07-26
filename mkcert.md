# Mkcert
## Install golang
- apt install golang
- tạo file /etc/profile.d/goenv.sh : 
```
export GOROOT=/usr/lib/go
export GOPATH=$HOME/go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
```
- source /etc/profile.d/goenv.sh

## Íntall Certutil
```
apt isntall libnss3-tools
```

## Install mkcert
```
wget https://github.com/FiloSottile/mkcert/archive/v1.0.0.tar.gz  
cd mkcert-1.0.0/  
make  
copy mkcert trong mkcert-1.0.0/bin đến /sr/bin  
```
- install: 
```
mkcert -install   
mkcert -CAROOT  
```
- tạo certificate: 
```
mkcert domain-name  
```
- copy domain-name.pem vào  /etc/ssl/certs/, domain-name-key.pem vào /etc/ssl/private/
- vào file /etc/apache2/sites-available/default-ssl.conf, edit SSLCertificateFile và SSLCertificateKeyFile theo tên certificate vừa tạo
- restart apache.