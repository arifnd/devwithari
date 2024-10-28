# Install PHP 5.6 on Debian 12 (bookworm)

1. Update the server:

```bash
sudo apt update && sudo apt upgrade -y
```

2. Add packages.sury.org repository for Debian:

```bash
curl -sSL https://packages.sury.org/php/README.txt | sudo bash -x
sudo apt update
```

3. Install PHP 5.6:
```bash
sudo apt install php5.6-cli
```
4. Check PHP version installed:
```bash
php -v
```

```

```
