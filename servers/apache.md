# 🔥APACHE Configuration file(httpd.conf)



This is the main Apache HTTP server configuration file.  It contains the configuration directives that give the server its instructions.

[REFERENCE](http://httpd.apache.org/docs/2.2) </br>
[HTTPD DIRECTIVES](http://httpd.apache.org/docs/2.2/mod/directives.html)

---

## Find Apache http.conf/apache2.conf Configuration File

* You can invoke **apache2** directly (which is not recommended in most cases) or administer it using **apache2ctl** control interface as below with the **-V** flag which shows the version and build parameters of apache2

    ```text
    --------- On CentOS/RHEL/Fedora ---------
    $ apachectl -V | grep SERVER_CONFIG_FILE

    --------- On Debian/Ubuntu/Linux Mint ---------
    $ apache2ctl -V | grep SERVER_CONFIG_FILE
    ```

---

## Configuration and logfile names

* If the filenames you specify for many of the server's control files begin with "/" (or "drive:/" for Win32), the server will use that explicit path.

* If the filenames do not begin with "/", the value of ServerRoot is prepended.

* So "logs/foo_log" with ServerRoot set to "/Applications/MAMP/Library" will be interpreted by the server as "/Applications/MAMP/Library/logs/foo_log".

---

## Directives

* **ServerRoot**: The top of the directory tree under which the server's configuration, error, and log files are kept.

* Do not add a slash at the end of the directory path.

* If you point ServerRoot at a non-local disk, be sure to point the LockFile directive at a local disk.

* If you wish to share the same ServerRoot for multiple httpd daemons, you will need to change at least LockFile and PidFile.

    ```text
    ServerRoot "/Applications/MAMP/Library"
    ```

* **PidFile**: The file in which the server should record its process identification number when it starts.

    ```text
    <IfModule !mpm_netware.c>
    PidFile logs/httpd.pid
    </IfModule>
    ```

* **Listen**: Allows you to bind Apache to specific IP addresses and/or ports, instead of the default. See also the <VirtualHost> directive.

* Change this to Listen on specific IP addresses as shown below to  prevent Apache from glomming onto all bound IP addresses.

    ```text
    Listen 12.34.56.78:80
    (OR)
    Listen 8888
    ```

---

## Dynamic Shared Object (DSO) Support

* To be able to use the functionality of a module which was built as a DSO you have to place corresponding `LoadModule` lines at this location.

* So the directives contained in it are actually available _before_ they are used.

* Statically compiled modules (those listed by `httpd -l`) do not need to be loaded here.

* Example: LoadModule &nbsp; `<path of the module>`

    ```text
    LoadModule authn_file_module modules/mod_authn_file.so

    LoadModule authn_dbm_module modules/mod_authn_dbm.so

    LoadModule authn_anon_module modules/mod_authn_anon.so

    LoadModule authn_dbd_module modules/mod_authn_dbd.so

    LoadModule authn_default_module modules/mod_authn_default.so

    LoadModule authz_host_module modules/mod_authz_host.so

    LoadModule authz_groupfile_module modules/mod_authz_groupfile.so

    LoadModule authz_user_module modules/mod_authz_user.so

    LoadModule authz_dbm_module modules/mod_authz_dbm.so

    LoadModule authz_owner_module modules/mod_authz_owner.so

    LoadModule authz_default_module modules/mod_authz_default.so

    LoadModule auth_basic_module modules/mod_auth_basic.so

    LoadModule auth_digest_module modules/mod_auth_digest.so

    LoadModule file_cache_module modules/mod_file_cache.so

    LoadModule cache_module modules/mod_cache.so

    LoadModule disk_cache_module modules/mod_disk_cache.so

    LoadModule mem_cache_module modules/mod_mem_cache.so

    LoadModule dbd_module modules/mod_dbd.so

    LoadModule bucketeer_module modules/mod_bucketeer.so

    LoadModule dumpio_module modules/mod_dumpio.so

    LoadModule echo_module modules/mod_echo.so

    LoadModule case_filter_module modules/mod_case_filter.so

    LoadModule case_filter_in_module modules/mod_case_filter_in.so

    LoadModule reqtimeout_module modules/mod_reqtimeout.so

    LoadModule ext_filter_module modules/mod_ext_filter.so

    LoadModule include_module modules/mod_include.so

    LoadModule filter_module modules/mod_filter.so

    LoadModule substitute_module modules/mod_substitute.so

    LoadModule charset_lite_module modules/mod_charset_lite.so

    LoadModule deflate_module modules/mod_deflate.so

    LoadModule log_config_module modules/mod_log_config.so

    LoadModule logio_module modules/mod_logio.so

    LoadModule env_module modules/mod_env.so

    LoadModule mime_magic_module modules/mod_mime_magic.so

    LoadModule cern_meta_module modules/mod_cern_meta.so

    LoadModule expires_module modules/mod_expires.so

    LoadModule headers_module modules/mod_headers.so

    LoadModule ident_module modules/mod_ident.so

    LoadModule usertrack_module modules/mod_usertrack.so

    LoadModule unique_id_module modules/mod_unique_id.so

    LoadModule setenvif_module modules/mod_setenvif.so

    LoadModule version_module modules/mod_version.so

    LoadModule proxy_module modules/mod_proxy.so

    LoadModule proxy_connect_module modules/mod_proxy_connect.so

    LoadModule proxy_ftp_module modules/mod_proxy_ftp.so

    LoadModule proxy_http_module modules/mod_proxy_http.so

    LoadModule proxy_scgi_module modules/mod_proxy_scgi.so

    LoadModule proxy_ajp_module modules/mod_proxy_ajp.so

    LoadModule proxy_balancer_module modules/mod_proxy_balancer.so

    LoadModule ssl_module modules/mod_ssl.so

    LoadModule mime_module modules/mod_mime.so

    LoadModule dav_module modules/mod_dav.so

    LoadModule status_module modules/mod_status.so

    LoadModule autoindex_module modules/mod_autoindex.so

    LoadModule asis_module modules/mod_asis.so

    LoadModule info_module modules/mod_info.so

    LoadModule cgi_module modules/mod_cgi.so

    LoadModule fastcgi_module modules/mod_fastcgi.so

    LoadModule cgid_module modules/mod_cgid.so

    LoadModule dav_fs_module modules/mod_dav_fs.so

    LoadModule vhost_alias_module modules/mod_vhost_alias.so

    LoadModule negotiation_module modules/mod_negotiation.so

    LoadModule dir_module modules/mod_dir.so

    LoadModule imagemap_module modules/mod_imagemap.so

    LoadModule actions_module modules/mod_actions.so

    LoadModule speling_module modules/mod_speling.so

    LoadModule userdir_module modules/mod_userdir.so

    LoadModule alias_module modules/mod_alias.so

    LoadModule rewrite_module modules/mod_rewrite.so

    LoadModule perl_module modules/mod_perl.so

    LoadModule wsgi_module modules/mod_wsgi.so

    LoadModule xsendfile_module modules/mod_xsendfile.so

    LoadModule php7_module        /Applications/MAMP/bin/php/php7.2.10/modules/libphp7.so
    ```

> [📃 Sample Httpd Config File](servers/apache2.conf)
