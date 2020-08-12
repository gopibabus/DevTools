# Splunk Essentials

<img src="./assets/images/Splunk_logo.jpg" alt="curl" width="700">

## How to create Splunk Account❓

* Visit [splunk.com](https://www.splunk.com/page/sign_up)

* Fill all the details mentioned in that form and login to splunk.com

## How to download Free splunk version❓

* Visit [Pricing Section](https://www.splunk.com/en_us/software/pricing.html) in [splunk.com](https://www.splunk.com)

* Click Splunk® Free

* Choose your operating system and download

## How to install splunk on linux machine❓

* After login to the machine, please make sure that you are running all commands as root user

    ```text
    sudo su -
    ```

* Download Splunk using wget (we can get this from splunk website)

    ```text
    wget -O splunk-7.2.1-be11b2c46e23-linux-2.6-amd64.deb 'https://www.splunk.com/bin/splunk/DownloadActivityServlet?architecture=x86_64&platform=linux&version=7.2.1&product=splunk&filename=splunk-7.2.1-be11b2c46e23-linux-2.6-amd64.deb&wget=true'
    ```

* Install splunk

    ```text
    dpkg -i splunk-7.2.1-be11b2c46e23-linux-2.6-amd64.deb
    ```

* Splunk is installed in following directory

    ```text
    /opt/splunk
    ```

* Start Splunk

    ```text
    cd /opt/splunk/bin

    ./splunk start
    ```

* Enable splunk to start on booting the OS

    ```text
    ./splunk enable boot-start
    ```

* Enable splunk to start with **systemctl** command

    ```text
    systemctl enable splunk
    ```

* Start Splunk with systemctl command

    ```text
    systemctl start splunk
    ```

## What are the essentials functions of splunk❓

* Collect
* Search
* Reporting
* Visualizations
* Alerting

## What are the main benefits of Splunk❓

* No hunting of logs

* Cross reference

* Trace issue across infrastructure

## What are the features available in splunk to search❓

* Simple Filtering
* Basic Constraints
* Advanced Search syntax
* Simple Report generation
* Dashboards

## First foot steps to start using splunk

* Add data to splunk search

* Create a new user and assign admin role to him

* Install add-on **Splunk add-on for Unix & Linux** and point the log directory to monitor the logs from linux

## How can we start seaching "boot" in splunk❓

    boot

## How can we use AND, OR in search❓

    boot AND shutdown

    boot OR shutdown

## How we can use parenthesis to search combined results❓

    (boot OR startup) AND (finished OR complete)

## What are the different time parameters in splunk❓

    last 24 hrs, last year, last 30 mins, last 30 secs or exact time interval etc.,

## How we can search based on the given time interval❓

    * earliest=-24h@h latest=-12h@h

## How can we search events from specific source and by specific application❓

    * source="/var/log/auth.log" AND process=sudo AND by vagrant

## How can we search based on event types❓

    * eventtype=pam_unix_authentication AND by vagrant
    (eventtype=pam_unix_authentication AND by vagrant) OR (shutdown AND target) AND earliest=-24h AND latest=-12h

## How to we use pipe "|" to filter and "NOT" to not include results from that user❓

    *  NOT user=vagrant | top  user

## How to search for PWD=/home/vagrant with regular expressions❓

    PWD | rex "PWD=(?<pwd>[^;]+)"

## How to search by omitting all duplicates related to host❓

    PWD | rex "PWD=(?<pwd>[^;]+)" | dedup host

## How to create sample Report❓

    bogomips NOT delay

    Search the query that you want and save as the report

## How to create a visualization from splunk❓

    404 AND sourcetype="access_combined" | timechart count

    Goto visualization page and can switch between different charts

    we can save as dashboard panels

    Go to dashboard panel and(...) add dashboard to home page for quick view. Now we are able to see all panels from that dashboard displaying on the home page

## How to create an alert❓

    sourcetype="access_combined" AND 404

    Save as an alert and set alert action as you preferred

## Points worth noted about Alerts❓

* we can create sms and push notifications

* we can create **meta data tokens** to display important notification information in alert

* we can integrate splunk with slack. we need to configure **incoming web hooks** on slack and paste that link to slack configuration in slack.

## How can we forward splunk logs to other splunk server❓

* Go to splunk and make sure to configure splunk forwarding port to 9997 in settings → Forwarding & receiving → configure receiving → New receiving port

* Install [splunk universal forwarder](https://www.splunk.com/en_us/download/universal-forwarder.html) on the server as like splunk we discussed previously

* Go to `/opt/splunkforwarder/bin`

* Type  `./splunk add forward-server 192.168.33.10:9997`

* Type `./splunk add monitor /var/log/` to monitor logs

## References

* [Splunk Docs](http://docs.splunk.com/Documentation)

* [Splunk Answers](https://answers.splunk.com/index.html)

* [Splunk Reference Manual](https://www.splunk.com/pdfs/solution-guides/splunk-quick-reference-guide.pdf)
