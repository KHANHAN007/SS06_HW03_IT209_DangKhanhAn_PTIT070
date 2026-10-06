root@anlinh:~# sudo ufw status verbose
echo "----------------"
sudo ss -tlnp | grep -E ':22|:8080'
echo "----------------"
curl -i http://localhost:8080
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)
New profiles: skip

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW IN    Anywhere                   # SSH
80/tcp                     ALLOW IN    Anywhere                  
8080/tcp                   ALLOW IN    Anywhere                   # Web Applicaiton
22/tcp (v6)                ALLOW IN    Anywhere (v6)              # SSH
80/tcp (v6)                ALLOW IN    Anywhere (v6)             
8080/tcp (v6)              ALLOW IN    Anywhere (v6)              # Web Applicaiton

----------------
LISTEN 0      5            0.0.0.0:8080      0.0.0.0:*    users:(("python3",pid=121937,fd=3))                      
LISTEN 0      128          0.0.0.0:22        0.0.0.0:*    users:(("sshd",pid=39092,fd=3))                          
LISTEN 0      128             [::]:22           [::]:*    users:(("sshd",pid=39092,fd=4))                          
----------------
HTTP/1.0 200 OK
Server: SimpleHTTP/0.6 Python/3.10.12
Date: Tue, 06 Oct 2026 08:54:27 GMT
Content-type: text/html
Content-Length: 33
Last-Modified: Tue, 06 Oct 2026 08:51:49 GMT

PTIT Web Application - Port 8080
root@anlinh:~# exit
logout
Connection to 160.187.229.99 closed.

