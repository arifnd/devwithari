# Install pgAdmin 4 Web Mode Only on Debian 12 (Bookworm)

### 1. Add the pgAdmin Repository Key:

```bash
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg
```

### 2. Add the pgAdmin Repository and Update the Package List:

```bash
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
```

### 3. Install pgAdmin 4

```bash
sudo apt install pgadmin4-web 
```

### 4. Configure pgAdmin for Web Mode:

```bash
sudo /usr/pgadmin4/bin/setup-web.sh
```

### 5. Change pgAdmin 4 Server Port (if there's a conflict with another web server):

Open the Apache ports configuration file:

```bash
sudo nano /etc/apache2/ports.conf
```

Update the listening port (e.g., to 8001):

```text
Listen 8001
```

Edit the Apache virtual host configuration:

```bash
sudo nano /etc/apache2/sites-available/000-default.conf
```

Update the virtual host to use the new port:

```text
<VirtualHost *:8001>
```

Restart Apache to apply the changes:

```bash
sudo systemctl restart apache2
```

### References

- [pgAdmin 4 Installation Guide](https://www.pgadmin.org/download/pgadmin-4-apt/)
- [Changing the pgAdmin 4 Server Port](https://stackoverflow.com/questions/66305141/pgadmin-4-server-mode-port)
