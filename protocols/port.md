# 🔥Port Forwarding

<img alt="port forwarding" width="800px" src="/assets/images/port_forwarding.png" />

### 🤷‍♂️How to expose website running on our machine to internet?

?> **NOTE:** For the Router and devices connected to Router have both internal and public ip addresses.

1. Identify the public ip address of our router.

<img alt="public ip" width="700px" src="/assets/images/public_ip.png" />

2. Identify your machine internal ip address.

> On windows just type **ipconfig** in your comamnd prompt.

<img alt="internal ip" width="700px" src="/assets/images/internal_ip.png" />

3. Run any application on your local ip address i.e either on 127.0.0.1 or 192.168.1.15(from 2nd step)

<img alt="website1" width="700px" src="/assets/images/website_1.png" />

<img alt="website2" width="700px" src="/assets/images/website_2.png" />

4. Create Port forwarding configuration in Router

<img alt="port forwarding" width="700px" src="/assets/images/port_forwarding_1.png" />

5. Try to access website from internet with router public ip address

?> When you make a request to Router using it's public ip address, it will forward that request/traffic to internal machine local ip address that we configured in the router

<img alt="public ip access" width="700px" src="/assets/images/public_ip_access.png" />

> In this way we can expose apps running on your machine to internet 😃

> [🌐 Reference Video](https://www.youtube.com/watch?v=92b-jjBURkw)
