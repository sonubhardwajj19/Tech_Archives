# Deployment

## IP Address
Every device on the internet has a number, like a house address. Example: 20.45.101.8. An IP address uniquely identifies a device on a network so data knows where to go.

    -IPv4: four numbers, like 192.168.1.1
    -Public IP: reachable from the internet    (your server needs one)
    -Private IP: only works inside a local network (like 192.168.x.x)

## Domain Names and Domain Name System (DNS)

  ### Domain name
    Humans can’t remember 20.45.101.8, so we use names like google.com. You buy a domain from a registrar (Namecheap, GoDaddy).

 ### DNS
    DNS is the phonebook of the internet. It converts a domain name into an IP address.

    What happens when you type myapp.me:

    The browser asks a DNS server: “What’s the IP of myapp.me?”
    DNS replies: “20.45.101.8”
    The browser connects to that IP.

 ### SubDomain 
    A subdomain is a prefix added before your main domain to organize different websites or services.     

    Example:- blog.google.com
    - google.com → Main domain
    - blog → Subdomain

    Used to separate different services or sections of a website 



## Virtual Machine (VM)
 VM is a computer rented from the cloud. A big physical machine is split into many virtual computers, and each one has its own OS (usually Linux), CPU, RAM and disk

   - EC2 is Amazon AWS’s VM service.
   - EC2 stands for Elastic compute Version 2.   Azure VM and DigitalOcean Droplets are the same idea with different names.


### Default Ports: 22, 80, 443
An IP address identifies the computer; a port helps identify the service on that computer.

  - Port 22 — SSH
    Used to securely connect to and manage a remote server.

  - Port 80 — HTTP
    Used for regular, unencrypted web traffic.

  - Port 443 — HTTPS
    Used for encrypted web traffic. Data is protected using TLS(Transport Layer Security)- cryptographic protocol that provides privacy, data integrity, and authentication for internet communications.
  
TLS is the security protocol. HTTPS is HTTP using TLS to secure communication.



## SSH-Secure Shell

It allows you to connect to another computer securely over a network and execute commands on it.

For example, your laptop is in front of you, but your EC2 server is running in AWS. SSH lets you control that server from your laptop.

- What is an SSH key pair?

    An SSH key pair consists of two related keys:
    - Public key: Placed on the server. It can be shared.
    - Private key: Kept securely on your own computer. Never share it.

The server uses the public key to verify that you possess the corresponding private key. This allows secure login without sending your private key to the server.


## Certificates

A TLS certificate is a digital document that helps a browser verify that a server is authorised to represent a particular domain.

For example, if your domain is example.com, its certificate identifies that domain and includes information used during the TLS handshake.
  
  ### Certbot
  Certbot is a tool that helps obtain and renew free TLS certificates from Let's Encrypt.    Instead of manually creating and installing certificates, you can use Certbot to automate much of the process.
  
  Why do we need Certbot if Let's Encrypt already provides certificates?

  Let's Encrypt issues the certificates; Certbot helps request, install, configure, and renew them.



## Reverse Proxy - Nginx

![Reverse Proxy](/Deveops/images/revProxy.png)

Reverse proxy means routing incoming client requests to the appropriate server running on a particular port.

NGINX is open source software for web serving, reverse proxying caching, load balancing, media streaming, and
more. It started out as a web server designed for maximum performance and stability. In addition to its HTTP server
capabilities, NGINX can also function as a proxy server for email (IMAP, POP3, and SMTP) and a reverse proxy and
load balancer for HTTP, TCP, and UDP servers.
