## To Use Cache for Nginx File Server Only Just When We Use The Theme

### Step 1: Identify the Caching Directory

The caching directory is usually located within the h5ai directory structure. Common locations include _h5ai/private/cache or _h5ai/public/cache.

### Step 2: Change Permissions
You need to set the correct permissions for the caching directory. First, navigate to the h5ai directory:

sh


```
cd /var/www/html/_h5ai
```

##### Then, adjust the permissions. Here’s how you can make the cache directory writable   by the web server:


### Check and Set Permissions

sh


```
sudo chown -R www-data:www-data private/cache
```
```
sudo chmod -R 755 private/cache
```



### If the cache directory is located somewhere else (e.g., public/cache), adjust the path accordingly:

sh

```
sudo chown -R www-data:www-data public/cache
```

```
sudo chmod -R 755 public/cache
```



### Step 3: Verify

Ensure the permissions have been set correctly by listing the directory with detailed permissions:

sh

```
ls -ld private/cache
```

#### and

sh
```
ls -ld public/cache
```


#### The output should indicate that the directory is writable by the www-data user.

### Step 4: Restart NGINX (if necessary)

In most cases, you don’t need to restart NGINX, but if you encounter any issues, it’s a good practice to do so:

sh
```
sudo systemctl restart nginx
```
