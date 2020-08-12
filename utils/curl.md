# 🔥CURL Essentials

<img src="./assets/images/curl_logo.png" alt="curl" width="700">

* Simple GET Request

    ```txt
    curl https://jsonplaceholder.typicode.com/posts
    curl https://jsonplaceholder.typicode.com/posts/1
    ```

* Include HTTP Header (--include, -i)

    ```txt
    curl --include https://jsonplaceholder.typicode.com/posts/1
    ```

* Header Only (--head, -I)

    ```txt
    curl --head https://jsonplaceholder.typicode.com/posts/1
    ```

* Write output to file (-o, --output)

    ```txt
    curl -o test.txt https://jsonplaceholder.typicode.com/posts/1
    ```

* Download File (-O, --remote-name)

    ```txt
    curl -O http://i.imgur.com/QRlAg0b.png
    ```

* Limit Transfer Rate

    ```txt
    curl -O --limit-rate 1000B http://i.imgur.com/QRlAg0b.png
    ```

* Spoof user agent

    ```txt
    curl -O test.txt http://traversymedia.com/test.txt -A "Mozilla"
    ```

* POST Data (-d, --data)

    ```txt
    curl -d "title=Hello&body=Hello World" https://jsonplaceholder.typicode.com/posts
    ```

* PUT Data (-X PUT -d)

    ```txt
    curl -X PUT -d "title=Hello&body=Hello World" https://jsonplaceholder.typicode.com/posts/1

    ```

* Delete Data (-X DELETE)

    ```txt
    curl -X DELETE https://jsonplaceholder.typicode.com/posts/1
    ```

* Secured Routes

    ```txt
    curl -u brad:mypassword https://jsonplaceholder.typicode.com/posts/1
    ```

* Follow Redirection (-L)

    ```txt
    curl http://google.com
    curl -L http://google.com
    ```

* Download Files From FTP Server

    ```txt
    curl -u ftpuser:ftppass -O ftp://x.x.x.x/public_html/sopmefile.php
    ```

* Upload via FTP

    ```txt
    curl -u test@traversymedia.com:123456! -T hello.txt ftp://ftp.traversymedia.com
    ```

* Download via FTP

    ```txt
    curl -u test@traversymedia.com:123456! -O ftp://ftp.traversymedia.com/hello.txt
    ```
