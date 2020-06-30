# 🔥Tunneling

## ⚡SSH Tunneling

?> Access resources on remote server or allow access to your local resources to someone else.

> [🌐 Resource Video](https://www.youtube.com/watch?v=N8f5zv9UUMI)

## ⚡How to use Expose?

<img src="./assets/images/expose-1.png" alt="Expose" width="700">

?> **Expose** is a multiplatform **tunnelling, reverse proxy software** that establishes secure tunnels from a public endpoint such as internet to a locally running network service while capturing all traffic for detailed inspection and replay.

?> In simple words, we can **expose web apps** running on our local machine to internet using randomly generated **expose** URL.

<img src="./assets/images/expose.png" alt="Expose" width="700">

!> In the above diagram, expose server is hosted on [beyondcode](https://beyondco.de/) and client is installed on our machine.

Following are the steps to install and configure **expose client** on our machine.

1. Sign up and login in to [beyondcode](https://beyondco.de/).
2. Visit dashboard area on the website.
3. Click Expose **License & Download**.
4. Copy expose token(********-****-****-****-************).
5. Install expose client with help of [composer](https://getcomposer.org/download/)

```bash
composer global require beyondcode/expose
```

6. Make sure that expose is accessible from the command line.

```bash
expose --version
```

7. Register your expose token. At this point your totally configured expose client.

```bash
expose token [your token]
```

8. Share your app running on your machine using expose.

```bash
expose share localhost:5501
```

> Above step will generate random Expose URL. With the help of this URL you can access your local web app from internet.

<img src="./assets/images/expose-share.png" alt="Expose" width="700">

?> There are many cool things we can do with **Expose**. We can configure our own server. We can access dashboards on server side and client side to monitor requests. We can provide authentication and many more.

> [🌐 Official Documentation](https://beyondco.de/docs/expose/introduction)

> [🌐 Blog post by Author](https://pociot.dev/28-introducing-expose-an-easy-to-use-tunneling-service-implemented-in-pure-php)

> [🌐 Expose Github Repo](https://github.com/beyondcode/expose)