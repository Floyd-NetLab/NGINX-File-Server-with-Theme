## How to use theme in nginx file server

### First Log in to your server via telnet or ssh

```
sudo apt install nginx
```
```
sudo apt update
```
```
sudo apt install php-fpm php-cli php-mbstring php-xml
```
```
sudo systemctl status nginx
```
```
sudo systemctl reload nginx
```
```
sudo nano /etc/nginx/sites-available/default
```
```
server {
    listen 80;
    server_name localhost;

    root /var/www/html;
    index index.html index.php /_h5ai/public/index.php;

    location / {
        try_files $uri $uri/ =404;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php8.1-fpm.sock;   # Ensure this matches your PHP-FPM socket path
    }

    location ~ /\.ht {
        deny all;
    }
}
```
```
sudo systemctl reload nginx
```
### Test the Nginx configuration for syntax errors
```
sudo nginx -t
```
### Reload Nginx
```
sudo systemctl reload nginx
```

##### Use Filezilla and access your server then go to var/www/html
##### Then create directory to upload your files for sharing
## How to add theme for your ftp server
##### Download this folder [ File Sharing Server Theme or File Sharing Server Theme Edited by Floyd ]
##### Then again use filezilla and go to var/www/html 
##### After that just copy the folder named _h5ai from the downloaded folder named [ File Sharing Server Theme ] or [ File Sharing Server Theme Edited by Floyd ] and paste the folder to var/www/html




