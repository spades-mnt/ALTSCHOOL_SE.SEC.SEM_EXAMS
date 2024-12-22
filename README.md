
This project is about how I deployed an html file to my AWS server by provisioning it with the Apache server. This readme seeks to show the processes i adopted in ensuring the completion of this project.

PROJECT URL: mackle.duckdns.org

STEP 1. CREATING AN EC2 INSTANCE ON AWS.

A. Create an ec2 instance on the AWS console in any of the regions. 

B. Download the keypair associated with the instance as it will be used to SSH into your instance created.

c. Allow port 80, 22, and 443 in the inbound security groups to ensure traffic from the internet.

D. Copy public ipv4 address assigned to your instance.


STEP 2. SSHING INTO YOUR INSTANCE

A. Head over to the linux terminal to ssh into your instance. first find the path where the keypair was downloaded to.

B. 'cd' into your path. eg (cd downloads)

C. 'ssh' into your instance. (ssh -i ./mikey.pem ubuntu@< public ip address > 



STEP 3.INSTALLING APACHE

A. First, update the package list. 'sudo apt update'

B. install apache. 'sudo apt install apache2 -y'.



STEP 4. CREATE AN HTML FILE AND ENSURE ITS ACCESSIBLE

A. Create an html file and save. 'sudo nano /var/www/html/index.html'

B. Head over to your AWS console and copy the public ipv4 address and paste in a browser. see if the content of your html file is displayed.


STEP 5. OBTAIN A DOMAIN NAME FOR YOUR SITE.

A. There are many ways to obtain a domain name for your site. one way is to use sites that do provise free domain names like duckdns.com

B. Create an account and iput the your preferred domain name. If available, input your ipv4 public address of your instance to make sure the name chosen is attached
   to the ip address.

C. To confirm if the domain nameof your site works, copy the domain or url and paste into your browser.

D. You can test the domain name by pinging it as well.


STEP 6. OBTAIN AN SSL CERTIFICATE 

A. Update your package list.

B. Install certbot. 'sudo apt install certbot python3-certbot-apache -y'

C. Install  or obtain SSL certificate and follow the prompt. 'sudo certbot --apache -d <your url>
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             

