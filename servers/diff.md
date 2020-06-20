# 🔥Apache vs Nginx HTTP Servers

!> There is no one-size-fits-all web server, so use the solution(Apache or Nginx) that best aligns with your objectives of the project.

<img src="./assets/images/diff.png" alt="diff" height="300" width="500">

- **Apache** and **Nginx** are the two most common open source web servers in the world.
- Together, they are responsible for serving over 50% of traffic on the internet.

## ⚡Apache
- The Apache HTTP Server was created by Robert McCool in 1995 and has been developed under the direction of the Apache Software Foundation since 1999.
- The Apache web server has been the most popular server on the internet since **1996**.
- It is extensible through a dynamically loadable module system.
- It can process a large number of interpreted languages without connecting out to separate software.

## ⚡Nginx
- In 2002, Igor Sysoev began work on Nginx as an answer to the [C10K problem](https://en.wikipedia.org/wiki/C10k_problem).
- The initial public release was made in **2004**, meeting this goal by relying on an asynchronous, events-driven architecture.
- Nginx has grown in popularity because of its light-weight resource utilization and its ability to scale easily on minimal hardware.
- Nginx excels at serving static content quickly.
- It is designed to pass dynamic requests off to other software that is better suited for those purposes.
- Advocates welcome Nginx’s focus on core web server and proxy features.

### ✳Connection Handling Architecture
**Apache**
- Apache provides a variety of multi-processing modules (MPMs) that dictate how client requests are handled.
- This allows administrators to swap out its connection handling architecture easily.

> **mpm_prefork**: This processing module spawns processes with a single thread each to handle request. Each child can handle a single connection at a time. As long as the number of requests is fewer than the number of processes, this MPM is very fast. PHP is not thread-safe, so this MPM is recommended as the only safe way of working with **mod_php**, the Apache module for processing these files.

> **mpm_worker**: This module spawns processes that can each manage multiple threads. Each of these threads can handle a single connection.

> **mpm_event**: This module is similar to the worker module in most situations, but is optimized to handle keep-alive connections. The event MPM handles keep alive connections by setting aside dedicated threads for handling keep alive connections and passing active requests off to other threads.

**Nginx**
- Nginx was designed from the ground up to use an asynchronous, non-blocking, event-driven connection handling algorithm.
- Nginx spawns worker processes, each of which can handle thousands of connections. The worker processes accomplish this by implementing a fast looping mechanism that continuously checks for and processes events.
- Decoupling actual work from connections allows each worker to concern itself with a connection only when a new event has been triggered.
- Since the server is single-threaded and processes are not spawned to handle each new connection, the memory and CPU usage tends to stay relatively consistent, even at times of heavy load.

### ✳Static vs Dynamic Content
**Apache**
- Apache servers can handle static content using its conventional file-based methods. The performance of these operations is mainly a function of the MPM methods described above.
- Apache can also process dynamic content by embedding a processor of the language in question into each of its worker instances. This allows it to execute dynamic content within the web server itself without having to rely on external components. These dynamic processors can be enabled through the use of dynamically loadable modules.

**Nginx**
- Nginx does not have any ability to process dynamic content natively. To handle PHP and other requests for dynamic content, Nginx must pass to an external processor for execution and wait for the rendered content to be sent back. The results can then be relayed to the client.
- Communication must be configured between Nginx and the processor over one of the protocols Nginx knows how to speak (http, FastCGI, SCGI, uWSGI, memcache).

### ✳Distributed vs Centralized Configuration
**Apache**
- Apache includes an option to allow additional configuration on a per-directory basis by inspecting and interpreting directives in hidden files within the content directories themselves. These files are known as **.htaccess** files.
- This effectively **allows decentralized configuration of the web server**, which is often used for implementing URL rewrites, access restrictions, authorization and authentication, even caching policies.
- Changes in **.htaccess** file are implemented immediately without reloading the server.

**Nginx**
- Nginx **does not interpret .htaccess files**, nor does it provide any mechanism for evaluating per-directory configuration outside of the main configuration file.
- By not allowing directory overrides(.htaccess), Nginx can serve requests faster by doing a single directory lookup and file read for each request.
- This effectively **allows centralized configuration of the web server**.

### ✳File vs URI-Based Interpretation
**Apache**
- Apache provides the ability to interpret a request as a physical resource on the filesystem.
- It begins by taking the document root and appending the portion of the request following the host and port number to try to find an actual file.
- An **Alias** directive can be used to map to an alternative location.
- **<Location>** blocks is a method of working with the URI itself instead of the filesystem.
- While Apache has the ability to operate on both the underlying filesystem and the webspace, it leans heavily towards filesystem methods.

**Nginx**
- Nginx was created to be both a web server and a proxy server.
- It works primarily with URIs, translating to the filesystem when necessary.
- Nginx does not provide a mechanism for specifying configuration for a filesystem directory and instead parses the URI itself.
- The primary configuration blocks for Nginx are server and location blocks. The server block interprets the host being requested, while the location blocks are responsible for matching portions of the URI that comes after the host and port. At this point, the request is being interpreted as a URI, not as a location on the filesystem.
- For static files, all requests eventually have to be mapped to a location on the filesystem. First, Nginx selects the server and location blocks that will handle the request and then combines the document root with the URI, adapting anything necessary according to the configuration specified.
- This may seem similar, but parsing requests primarily as URIs instead of filesystem locations allows Nginx to more easily function in both web, mail, and proxy server roles.

### ✳Modules
**Apache**
- Apache’s module system allows you to dynamically load or unload modules to satisfy your needs during the course of running the server.
- The Apache core is always present, while modules can be turned on or off, adding or removing additional functionality and hooking into the main server.
- Modules can be used to alter some of the core functionality of the server, such as mod_php, which embeds a PHP interpreter into each running worker.
- Modules can be used used for rewriting URLs, authenticating clients, hardening the server, logging, caching, compression, proxying, rate limiting, and encrypting.

**Nginx**
- In Nginx, modules are not dynamically loadable, so they must be selected and compiled into the core software.
- Nginx modules are very useful and they allow you to dictate what you want out of your server by only including the functionality you intend to use.
- Nginx modules can provide proxying support, compression, rate limiting, logging, rewriting, geolocation, authentication, encryption, streaming, and mail functionality.

### ✳Support, Compatibility, Ecosystem, and Documentation
**Apache**
- Because Apache has been popular for so long, support for the server is fairly ubiquitous.
- There is a large library of first- and third-party documentation available for the core server and for task-based scenarios involving hooking Apache up with other software.
- Many people start off their business in shared-hosting, which almost exclusively rely on Apache due to the **.htaccess** distributed management capabilities.

**Nginx**
- Nginx is experiencing increased support as more users adopt it for its performance profile.
- As interest in the project grew, the documentation has been filled out and there are now plenty of administration resources on the Nginx site and through third parties.
- In regards to third-party applications, support and documentation is becoming more readily available, and package maintainers are beginning, in some cases, to give choices between auto-configuring for Apache and Nginx.

## ⚡Using Apache and Nginx Together
- The conventional configuration for this partnership is to place **Nginx in front of Apache as a reverse proxy**. This will allow Nginx to to handle all requests from clients. This takes advantage of Nginx’s fast processing speed and ability to handle large numbers of connections concurrently.
- For static content, which Nginx excels at, the files will be served quickly and directly to the client.
- For dynamic content, for instance PHP files, Nginx will proxy the request to Apache, which can then process the results and return the rendered page. Nginx can then pass the content back to the client.
- Nginx will handle all requests it can and pass on the ones that it has no native ability to serve. By cutting down on the requests the Apache server is asked to handle.
- This configuration also allows you to scale out by adding additional backend servers as necessary.

> [🌐 Reference](https://www.digitalocean.com/community/tutorials/apache-vs-nginx-practical-considerations)