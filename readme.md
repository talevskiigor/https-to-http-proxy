# Setup
## Download
Open web page: [https://nginx.org/en/download.html](https://nginx.org/en/download.html)

Select legacy version for Windows:
[	nginx/Windows-1.24.0](https://nginx.org/download/nginx-1.24.0.zip)

## Install
Extract zip file to `c:\`

Optional, rename the folder
from: 

`nginx-1.24.0` to `nginx`

Now start `c:\nginx\nginx.exe` 
>Note: frist time  will need to confirm security access.

Test the setup by opening [http://localhost/](http://localhost/)

*You should see Nginx Welcome page.*


> Welcome to nginx!  
If you see this page, the nginx web server is successfully 
installed and working. 

## Configuration
Now, stop the server (kill from task menager)

Copy *ssl* folder into nginx foder `c:\nginx\`

Copy (overwrite) `conf\nginx.conf` to  `c:\nginx\conf\nginx.conf`

Edit the file Read more [nginx.conf](./conf/nginx.conf)
and replace accrding to your needs:
#### HTTPS Server Configuration

```nginx 
listen 5001 ssl; # this is the local port on the local PC

server_name localhost; # this is the name of the local server
```


#### Location
```nginx 
proxy_pass http://127.0.0.1:3000;  
# remote server where to be forward request in format prtocol:://address[hostname]:port
```

#### Start nxing

- Since Windows doesn’t have a built-in way to run NGINX as a service, we use NSSM.
Download NSSM from: [https://nssm.cc/download](https://nssm.cc/download)

- Other way is to simple add to startup application


# Testing
For local testing to have a fake server it can be used simple [JSON server](https://github.com/typicode/json-server)