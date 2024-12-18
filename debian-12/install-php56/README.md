# Install PHP 5.6 on Debian 12 (Bookworm)

### 1. Update the Server

```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Install depedencies

```bash
sudo apt install -y apt-transport-https lsb-release ca-certificates curl
```

### 3. Add the `packages.sury.org` Repository for Debian

```bash
curl -sSL https://packages.sury.org/php/README.txt | sudo bash -x
```

### 4. Install PHP 5.6

```bash
sudo apt install php5.6-cli
```

### 5. Check the Installed PHP Version

```bash
php -v
```

Example output:

```
PHP 5.6.40-78+0~20240802.86+debian12~1.gbp864daf (cli) 
Copyright (c) 1997-2016 The PHP Group
Zend Engine v2.6.0, Copyright (c) 1998-2016 Zend Technologies
    with Zend OPcache v7.0.6-dev, Copyright (c) 1999-2016, by Zend Technologies
```
