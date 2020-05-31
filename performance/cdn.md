# 🔥Peformance - Backend

<img src="./assets/images/performance_3.png" alt="performance" width="700">

## ⚡Content Delivery Network(CDN)

<img src="./assets/images/cdn.gif" alt="cdn" width="700">

?> A **content delivery network (CDN)** refers to a geographically distributed group of servers which work together to provide fast delivery of Internet content.

?> CDNs serve a large portion of the Internet content today, including **web objects (text, graphics and scripts)**, downloadable objects (media files, software, documents), applications (e-commerce, portals), live streaming media, on-demand streaming media, and social media sites.

### ✳Big players in CDN space

> [🌐 Cloudfare](https://www.cloudflare.com/)

> [🌐 Amazon Cloudfront](https://aws.amazon.com/cloudfront/)

> [🌐 Azure CDN](https://docs.microsoft.com/en-us/azure/cdn/)

## ⚡GZIP

?> Compression is a simple, effective way to save bandwidth and speed up your site. If we could send a **.zip file** to the browser **(index.html.zip)** instead of plain old **index.html**, we’d save on bandwidth and download time. The browser could download the zipped file, extract it, and then show it to user, who’s in a good mood because the page loaded quickly.

### ✳Without GZIP

<img src="./assets/images/http_old.png" alt="http old" width="500">

### ✳With GZIP

<img src="./assets/images/http_gzip.png" alt="gzip" width="500">

?> The tricky part of this exchange is the browser and server knowing it’s ok to send a zipped file over. The agreement has two parts

1. The browser sends a header telling the server it accepts compressed content (gzip and deflate are two compression schemes): _Accept-Encoding: gzip, deflate_
2. The server sends a response if the content is actually compressed: _Content-Encoding: gzip_

### ✳Enable GZIP in Apache

> In **Apache**, enabling output compression is fairly straightforward. Add the following to your **.htaccess** file:

```bash
# compress text, html, javascript, css, xml:
AddOutputFilterByType DEFLATE text/plain
AddOutputFilterByType DEFLATE text/html
AddOutputFilterByType DEFLATE text/xml
AddOutputFilterByType DEFLATE text/css
AddOutputFilterByType DEFLATE application/xml
AddOutputFilterByType DEFLATE application/xhtml+xml
AddOutputFilterByType DEFLATE application/rss+xml
AddOutputFilterByType DEFLATE application/javascript
AddOutputFilterByType DEFLATE application/x-javascript

# Or, compress certain file types by extension:
<files *.html>
SetOutputFilter DEFLATE
</files>
```

> **Apache** actually has two compression options:

1. **mod_deflate** is easier to set up and is standard.
2. **mod_gzip** seems more powerful: you can pre-compress content.

!> Apache checks if the browser sent the **“Accept-encoding”** header and returns the compressed or regular version of the file.

### ✳Verify Your Compression

<img src="./assets/images/chrome-gzip-header.png" alt="chrome-gzip-header" width="700">

> [🌐 Reference Documentation](https://betterexplained.com/articles/how-to-optimize-your-site-with-gzip-compression/)

### Brotli

?> **Brotli** from google is a generic-purpose lossless compression algorithm that compresses data using a combination of a modern variant of the LZ77 algorithm, Huffman coding and 2nd order context modeling, with a compression ratio comparable to the best currently available general-purpose compression methods. It is similar in speed with deflate but offers more dense compression.

```
content-encoding: br
```

> [🌐 Reference](https://github.com/google/brotli)
