[< Back to menu](../README.md)

---

# LAMP Server

Linux, Apache, MySql, PHP Server.

## 1. Apache

HTTP Server.

<table>
    <tr><td><code>apt install apache2</code></td><td>install apache2 HTTP Server</td></tr>
    <tr><td><code>a2*</code></td><td>apache2 utils for management</td></tr>
</table>

## 2. PHP

Extend our Apache server with PHP mod.

<table>
    <tr><td><code>apt install libapache2-mod-php</code></td><td>install PHP mod for Apache Server</td></tr>
</table>


## 3. MySql

MySql database. Defaults usually to [MariaDB](https://mariadb.org/).

<table>
    <tr><td><code>apt install default-mysql-server</code></td><td>install MySql Server</td></tr>
</table>


## 4. MediaWiki

Wiki hosted on our server. Download from [MediaWiki website](https://www.mediawiki.org/wiki/Download).

### Setup DB

<table>
    <tr><td><code>apt install php-mysql php-mbstring php-xml</code></td><td>instal php modules</td></tr>
    <tr><td><code>service apache2 reload</code></td><td>reload apache to load php modules</td></tr>
    <tr><td><code>mysql -u root -p</code></td><td>open mysql console</td></tr>
    <tr><td>
        <code>MariaDB [(none)]> USE mysql;</code><br/>
        <code>MariaDB [mysql]> CREATE USER 'wiki'@'localhost' IDENTIFIED BY 'wiki';</code>
    </td><td>create database user for wiki</td></tr>
    <tr><td>
        <code>MariaDB [(none)]> CREATE DATABASE wiki;</code><br/>
        <code>MariaDB [(none)]> USE wiki;</code><br/>
        <code>MariaDB [wiki]> GRANT ALL ON wiki.* TO wiki@localhost;</code>
    </td><td>create database for wiki</td></tr>
</table>

### Setup Website

<table>
    <tr><td><code>/etc/apache2/sites-available</code></td><td>sites configurations used by apache</td></tr>
    <tr><td><code>/etc/apache2/sites-available/wiki.example.com.conf</code></td><td>create <a href="../files/lamp/wiki.example.com.conf">confuration file</a></td></tr>
    <tr><td><code>service apache2 reload</code></td><td>reload apache server</td></tr>
    <tr><td><code>wget -O mediawiki.zip https://releases.wikimedia.org/mediawiki/1.35/mediawiki-1.35.1.zip</code></td><td>dowload wiki website</td></tr>
    <tr><td><code>unzip mediawiki.zip -d /var/www/wiki</code></td><td>unpack wiki to website directory</td></tr>
</table>

Open `wiki.example.com` in browser and configure your wiki.

---

[< Back to menu](../README.md)

---

<p align="center">
    <b><a href="https://github.com/MGSE97" target="_blank">MGSE97</a> 🔥 2021</b>
</div>
