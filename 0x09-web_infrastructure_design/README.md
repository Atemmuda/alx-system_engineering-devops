# 0x09. Web infrastructure design
## This directory contains script file for runnig a complete web infrastructure

### Descriptions

#### 0-simple_web_stack
Design a one server web infrastructure that hosts the website that is reachable via www.foobar.com

* The web server has:
1. 1 server
2. 1 web server (Nginx)
3. 1 application server
4. 1 application files (your code base)
5. 1 database (MySQL)
6. 1 domain name foobar.com configured with a www record that points to your server IP 8.8.8.8

* Explanation has been given for:
1. What is a server
2. What is the role of the domain name
3. What type of DNS record www is in www.foobar.com
4. What is the role of the web server
5. What is the role of the application server
6. What is the role of the database
7. What is the server using to communicate with the computer of the user requesting the website

* Explanation is given  for the possible issues with this infrastructure:
1. SPOF
2. Downtime when maintenance needed (like deploying new code web server needs to be restarted)
3. Cannot scale if too much incoming traffic

#### 1-distributed_web_infrastructure
Design a three server web infrastructure that hosts the website www.foobar.com.

* The web server has:
1. 2 servers
2. 1 web server (Nginx)
3. 1 application server
4. 1 load-balancer (HAproxy)
5. 1 set of application files (your code base)
6. 1 database (MySQL)

* Explanation has been given for:
1. For every additional element, why you are adding it
2. What distribution algorithm your load balancer is configured with and how it works
3. Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both
4. How a database Primary-Replica (Master-Slave) cluster works
5. What is the difference between the Primary node and the Replica node in regard to the application

* Explanation is given  for the possible issues with this infrastructure:
1. Where are SPOF
2. Security issues (no firewall, no HTTPS)
3. No monitoring

#### 2-secured_and_monitored_web_infrastructure
Design a three server web infrastructure that hosts the website www.foobar.com, it must be secured,serve encrypted traffic, and be monitored.

* The web server has:
1. 3 firewalls
2. 1 SSL certificate to serve www.foobar.com over HTTPS
3. 3 monitoring clients (data collector for Sumologic or other monitoring services)

* Explanation has been given for:
1. For every additional element, why you are adding it
2. What are firewalls for
3. Why is the traffic served over HTTPS
4. What monitoring is used for
5. How the monitoring tool is collecting data
6. What to do if you want to monitor your web server QPS

* Explanation is given  for the possible issues with this infrastructure:
1. Why terminating SSL at the load balancer level is an issue
2. Why having only one MySQL server capable of accepting writes is an issue
3. Why having servers with all the same components (database, web server and application server) might be a problem