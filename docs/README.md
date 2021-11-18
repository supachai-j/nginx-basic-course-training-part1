# NGINX Basic Course Training part  1 - Lab guides

### 1. Installation NGINX and NGINX Plus
---
1.1 Installing a Prebuilt Ubuntu Package from the Official NGINX Repository.

Refer Step: https://docs.nginx.com/nginx/admin-guide/installing-nginx/installing-nginx-open-source/#prebuilt_ubuntu 

เพิ่มเติม ตั้งค่าในส่วนของ  ``/etc/apt/sources.list``
```
deb [arch=amd64] https://nginx.org/packages/mainline/ubuntu/ bionic nginx
deb-src https://nginx.org/packages/mainline/ubuntu/ bionic nginx
```
```
## For NGINX Plus Repo.
$ printf "deb [arch=amd64] https://pkgs.nginx.com/plus/ubuntu `lsb_release -cs` nginx-plus\n" | sudo tee /etc/apt/sources.list.d/nginx-plus.list

## For NGINX App Protect Repo.
$ printf "deb [arch=amd64] https://pkgs.nginx.com/app-protect/debian `lsb_release -cs` nginx-plus\n" | sudo tee /etc/apt/sources.list.d/nginx-app-protect.list

$ printf "deb [arch=amd64] https://pkgs.nginx.com/app-protect-security-updates/debian `lsb_release -cs` nginx-plus\n" | sudo tee -a /etc/apt/sources.list.d/nginx-app-protect.list
```

```
$ sudo systemctl enable nginx --now
$ sudo systemctl status nginx

$ nginx -v
nginx version: nginx/1.21.1
```

1.2 Installation NGINX Plus on Ubuntu 18.04.

Refer Step: https://docs.nginx.com/nginx/admin-guide/installing-nginx/installing-nginx-plus

จำเป็นต้องมี NGINX Plus License key and cert ก่อน สามารถขอ Trial ได้ที่ https://www.nginx.com/free-trial-request

แก้ไข เพิ่มเติมในส่วนของ  ```/etc/apt/sources.list.d/nginx-plus.list```
```
deb [arch=amd64] https://pkgs.nginx.com/plus/ubuntu bionic nginx-plus
```

```
$ sudo systemctl enable nginx --now
$ sudo systemctl status nginx

$ nginx -v
nginx version: nginx/1.19.10 (nginx-plus-r24-p1)

```
