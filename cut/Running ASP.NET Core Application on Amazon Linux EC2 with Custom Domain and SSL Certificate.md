# Running ASP.NET Core Application on Amazon Linux EC2 with Custom Domain and SSL Certificate
Running ASP.NET Core Application on Amazon Linux EC2 with Custom Domain and SSL Certificate

![](https://resonant-cement-f3c.notion.site/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F5e214f7d-dc43-4dec-b9b2-c4932f9ce967%2F5b280029-05a3-4a8c-bac6-896acbd198b5%2Fwhite_aws.png?table=block&id=8b651cbb-98be-473a-a8c6-872f5bf9ea30&spaceId=5e214f7d-dc43-4dec-b9b2-c4932f9ce967&width=40&freeze=true&userId=&cache=v2)

Running ASP.NET Core Application on Amazon Linux EC2 with Custom Domain and SSL Certificate

Made with

![](https://resonant-cement-f3c.notion.site/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F5e214f7d-dc43-4dec-b9b2-c4932f9ce967%2F32d83166-8ab6-4a01-853a-71b6fec04176%2Fchannels4_profile_-_Copy.jpg?table=block&id=8b651cbb-98be-473a-a8c6-872f5bf9ea30&spaceId=5e214f7d-dc43-4dec-b9b2-c4932f9ce967&width=2000&userId=&cache=v2)

![](https://resonant-cement-f3c.notion.site/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F5e214f7d-dc43-4dec-b9b2-c4932f9ce967%2F5b280029-05a3-4a8c-bac6-896acbd198b5%2Fwhite_aws.png?table=block&id=8b651cbb-98be-473a-a8c6-872f5bf9ea30&spaceId=5e214f7d-dc43-4dec-b9b2-c4932f9ce967&width=250&freeze=true&userId=&cache=v2)

Running ASP.NET Core Application on Amazon Linux EC2 with Custom Domain and SSL Certificate
===========================================================================================

📢

Running ASP.NET Core Application on Amazon Linux EC2 with Custom Domain and SSL Certificate | .NET 8 | Nginx | Let’s Encrypt

[

Step 1. Create an EC2 instance - Amazon Linux 2023



](/Running-ASP-NET-Core-Application-on-Amazon-Linux-EC2-with-Custom-Domain-and-SSL-Certificate-8b651cbb98be473aa8c6872f5bf9ea30?pvs=25#ed470d7d34074c63828e8b10a07c926e)

[

Step 2. Install Nginx



](/Running-ASP-NET-Core-Application-on-Amazon-Linux-EC2-with-Custom-Domain-and-SSL-Certificate-8b651cbb98be473aa8c6872f5bf9ea30?pvs=25#8bf508dbcf514236b2f9614b1f7b9348)

[

Step 3. Create a .NET 8 API, publish it, and upload it to the S3 bucket



](/Running-ASP-NET-Core-Application-on-Amazon-Linux-EC2-with-Custom-Domain-and-SSL-Certificate-8b651cbb98be473aa8c6872f5bf9ea30?pvs=25#adb9cbe27977421391e6b26af857938e)

[

Step 4. Make required directories on the Server



](/Running-ASP-NET-Core-Application-on-Amazon-Linux-EC2-with-Custom-Domain-and-SSL-Certificate-8b651cbb98be473aa8c6872f5bf9ea30?pvs=25#837da38d0f574badb86e8b4b90386bbd)

[

Step 5. Copy the Application Code into a directory



](/Running-ASP-NET-Core-Application-on-Amazon-Linux-EC2-with-Custom-Domain-and-SSL-Certificate-8b651cbb98be473aa8c6872f5bf9ea30?pvs=25#12c4a853adc44c7da06a473be0cd925a)

[

Step 6. Run the application manually



](/Running-ASP-NET-Core-Application-on-Amazon-Linux-EC2-with-Custom-Domain-and-SSL-Certificate-8b651cbb98be473aa8c6872f5bf9ea30?pvs=25#62e2e38d26734df9a5f90bd0aec8caf0)

[

Step 7. Configure the application to start automatically



](/Running-ASP-NET-Core-Application-on-Amazon-Linux-EC2-with-Custom-Domain-and-SSL-Certificate-8b651cbb98be473aa8c6872f5bf9ea30?pvs=25#2a9c15d325574f8282cb9e20c3683928)

[

Step 8. Update Nginx configuration to point to ASP.NET Core application



](/Running-ASP-NET-Core-Application-on-Amazon-Linux-EC2-with-Custom-Domain-and-SSL-Certificate-8b651cbb98be473aa8c6872f5bf9ea30?pvs=25#02adde41e62646d4bb13fec7c0665837)

[

Step 9. Run ASP.NET application with Custom Domain



](/Running-ASP-NET-Core-Application-on-Amazon-Linux-EC2-with-Custom-Domain-and-SSL-Certificate-8b651cbb98be473aa8c6872f5bf9ea30?pvs=25#6aaf9dcf9c63428ebcbe8c3826fd761c)

[

Step 10. Run with HTTP using an SSL Certificate



](/Running-ASP-NET-Core-Application-on-Amazon-Linux-EC2-with-Custom-Domain-and-SSL-Certificate-8b651cbb98be473aa8c6872f5bf9ea30?pvs=25#398ac6c6f1d940d9a61aa3e645cc5b9b)

#### Step 1. Create an EC2 instance - Amazon Linux 2023

Open [.NET 8 Support on AWS Guide](https://d1.awsstatic.com/getting-started-guides/dot-net-images/NET%208%20Support%20on%20AWS%20Guide.pdf) document, and copy the User Data script.

Bash

Copy

#!/bin/bash  sudo  rpm --import https://packages.microsoft.com/keys/microsoft.asc sudo  wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/37/prod.repo sudo dnf install -y dotnet-sdk-8.0 dotnet --version \> /tmp/dotnet-version

​

For troubleshooting: Check the User Data script logs by running sudo cat /var/log/cloud-init-output.log

Configure SSH - Create an IAM Role with [AmazonSSMManagedInstanceCore](https://docs.aws.amazon.com/aws-managed-policy/latest/reference/AmazonSSMManagedInstanceCore.html) [](https://docs.aws.amazon.com/aws-managed-policy/latest/reference/AmazonSSMManagedInstanceCore.html) managed policy. 

Ensure .NET 8 is installed, run dotnet --info

Create a security group to allow access on port 22/80/443.

#### Step 2. Install Nginx

💡

yum and apt, both are package managers for Linux. dnf is an improved version of yum.

Install the Nginx server. Run sudo dnf install nginx

Bash

Copy

sudo systemctl status nginx sudo systemctl enable  nginx sudo systemctl start nginx

​

Verify Nginx server is working.

#### Step 3. Create a .NET 8 API, publish it, and upload it to the S3 bucket

Create a .NET 8 app in Visual Studio

Publish it, make a zip file

Upload on S3 bucket

#### Step 4. Make required directories on the Server

Run the below commands one by one to create the necessary application folders.

Bash

Copy

\# go to root  cd / \# create 2 directories  sudo  mkdir wwwroot sudo  mkdir wwwroot-temp \# move to newly created directory  cd wwwroot \# create another directory inside wwwroot for the web-application  sudo  mkdir  <application-name\>

​

#### Step 5. Copy the Application Code into a directory

Update the application code (Use the below script to update the application code as well)

Bash

Copy

\# go to root again  cd / \# go to temp directory  cd wwwroot-temp \# copy the published file in application directory  sudo  rm /wwwroot-temp/\* sudo  wget -O "PublishedAPI.zip"  "https://{pre-signed-url}"  sudo  rm /wwwroot/<application-name\>/\* sudo  unzip PublishedAPI.zip -d /wwwroot/<application-name\>  sudo  rm PublishedAPI.zip

​

#### Step 6. Run the application manually

Bash

Copy

cd /wwwroot/<application-name\>  sudo dotnet <assembly-name\>.dll --urls http://0.0.0.0:5000

​

Try to access the application from the EC2 IP address.

#### Step 7. Configure the application to start automatically

💡

Refer to [Configure the ASP.NET Core application to start automatically](https://learn.microsoft.com/en-us/troubleshoot/developer/webapps/aspnetcore/practice-troubleshoot-linux/2-3-configure-aspnet-core-application-start-automatically) for more detail

Run sudo nano /etc/systemd/system/<daemon\_name>.service to create a daemon service.

Copy and paste this inside the editor. Refer to [How to paste into nano from clipboard?](https://superuser.com/a/1262167)

YAML

Copy

\[Unit\] Description=Example of ASP.NET Core MVC App running on Amazon Linux \[Service\] WorkingDirectory=/wwwroot/<application\-name\> ExecStart=/usr/bin/dotnet /wwwroot/<application\-name\>/<assembly\-name\>.dll \-\-urls "http://localhost:5000" Restart=always RestartSec=10 KillSignal=SIGINT SyslogIdentifier=<application\-name\> Environment=ASPNETCORE\_ENVIRONMENT=Production \[Install\] WantedBy=multi\-user.target

​

Use ctrl + o to write, and ctrl + x to exit.

Start the daemon service.

Bash

Copy

sudo systemctl enable  <daemon\_name\>  sudo systemctl start <daemon\_name\>  sudo systemctl status <daemon\_name\>

​

#### Step 8. Update Nginx configuration to point to ASP.NET Core application

💡

Refer to [Install Nginx and configure it as a reverse proxy server](https://learn.microsoft.com/en-us/troubleshoot/developer/webapps/aspnetcore/practice-troubleshoot-linux/2-2-install-nginx-configure-it-reverse-proxy) for more details.

Run whereis nginx to discover where the program is installed.

Open the Nginx configuration file in the nano editor. Run the below command.

Bash

Copy

sudo  nano /etc/nginx/nginx.conf

​

Use the below configuration to update the Nginx config file.

Bash

Copy

http { map $http\_connection  $connection\_upgrade  {  "~\*Upgrade"  $http\_connection; default keep-alive;  } server { listen 80; server\_name \_; location / { proxy\_pass http://localhost:5000; proxy\_http\_version 1.1; proxy\_set\_header Upgrade $http\_upgrade; proxy\_set\_header Connection $connection\_upgrade; proxy\_set\_header Host $host; proxy\_cache\_bypass $http\_upgrade; proxy\_set\_header X-Forwarded-For $proxy\_add\_x\_forwarded\_for; proxy\_set\_header X-Forwarded-Proto $scheme;  }  }  }

​

Restart the nginx service and verify.

Bash

Copy

sudo systemctl restart nginx

​

Verify by accessing the application from the EC2 IP address, or EC2 domain.

#### Step 9. Run ASP.NET application with Custom Domain

Create a new A record that points to EC2. i.e. api.yourdomain.com

Update server\_name to restrict access to specific domains.

[

Server names

Server names are defined using the server\_name directive and determine which server block is used for a given request. See also “How nginx processes a request”. They may be defined using exact names, wildcard names, or regular expressions:

![](https://resonant-cement-f3c.notion.site/image/https%3A%2F%2Fnginx.org%2Ffavicon.ico?table=block&id=2d38a883-f499-498f-9b25-128ebf1cda1b&spaceId=5e214f7d-dc43-4dec-b9b2-c4932f9ce967&userId=&cache=v2)

https://nginx.org/en/docs/http/server\_names.html





](https://nginx.org/en/docs/http/server_names.html)

#### Step 10. Run with HTTP using an SSL Certificate

[

Update: Using Free Let’s Encrypt SSL/TLS Certificates with NGINX - NGINX

Learn how to use the Let’s Encrypt client to generate RSA certificates and automatically configure NGINX to use the newly issued certificates.

![](https://resonant-cement-f3c.notion.site/image/https%3A%2F%2Fwww.nginx.com%2Fwp-content%2Fuploads%2F2019%2F10%2Ffavicon-64x46.ico?table=block&id=f20917b7-5f8f-478b-94b4-3a6b1f827d1f&spaceId=5e214f7d-dc43-4dec-b9b2-c4932f9ce967&userId=&cache=v2)

https://www.nginx.com/blog/using-free-ssltls-certificates-from-lets-encrypt-with-nginx/

![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)






](https://www.nginx.com/blog/using-free-ssltls-certificates-from-lets-encrypt-with-nginx/)

Reset everything, uninstall, and install.

Bash

Copy

sudo dnf remove nginx sudo dnf install nginx

​

Create a file in the /etc/nginx/conf.d directory named domain‑name.conf (so in our example, www.example.com.conf).

Bash

Copy

server { listen 80; server\_name <yourdomain.com\>; location / { proxy\_pass http://localhost:5000; proxy\_http\_version 1.1;  proxy\_set\_header Upgrade $http\_upgrade;  proxy\_set\_header Connection $connection\_upgrade; proxy\_set\_header Host $host;  proxy\_cache\_bypass $http\_upgrade; proxy\_set\_header X-Forwarded-For $proxy\_add\_x\_forwarded\_for; proxy\_set\_header X-Forwarded-Proto $scheme;  }  }

​

Save the file, then run this command to verify the syntax of your configuration and restart NGINX.

Bash

Copy

sudo nginx -t &&  sudo nginx -s reload

​

Install Let’s Encrypt Client

JSON

Copy

sudo dnf install certbot sudo dnf install python-certbot-nginx

​

Run the following command to generate certificates with the NGINX plug‑in.

JSON

Copy

sudo certbot --nginx -d yourdomain.com -d www.yourdomain.com

​

VertiTab

↑↓⇔⇧⇩