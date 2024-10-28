# Install PostgreSQL on Debian 12 (Bookworm)

### 1. Update Your System

```bash
sudo apt update && sudo apt upgrade
```

### 2. Install PostgreSQL

```bash
sudo apt install postgresql postgresql-contrib
```

### 3. Start and Enable the PostgreSQL Service

Check the service status:

```bash
sudo systemctl status postgresql
```

If it’s not running, start it with:

```bash
sudo systemctl start postgresql
```

Enable the service to start on boot:

```bash
sudo systemctl enable postgresql
```

### 4. Secure PostgreSQL

Switch to the PostgreSQL user and open the PostgreSQL shell:

```bash
sudo -i -u postgres
psql
```

Set a password for the PostgreSQL user:

```sql
\password postgres
```

### 5. Create a Database and Test the Connection

In the PostgreSQL shell, create a new database:

```sql
CREATE DATABASE mytestdb;
```

Exit the PostgreSQL shell:

```sql
\q
```

Then, test the connection to the new database:

```bash
psql -d mytestdb -U postgres
```

### 6. Enable Password-Based Login

Edit the `pg_hba.conf` file to allow password authentication. Replace `/15/` in the path with your installed PostgreSQL version:

```bash
sudo nano /etc/postgresql/15/main/pg_hba.conf
```

Ensure the following line is set:

```plaintext
local   all             postgres                                md5
```

After editing, restart the PostgreSQL service:

```bash
sudo systemctl restart postgresql
```

Test the connection to verify everything is working:

```bash
psql -d mytestdb -U postgres
```
