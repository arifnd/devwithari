# Install Puppeteer on Debian 12 (Bookworm)

### 1. Update the Server

```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Install Node.js

```bash
sudo apt install -y nodejs
```

### 3. Install Required System Packages

```bash
sudo apt install libasound2 libatk-bridge2.0-0 libatk1.0-0 libatspi2.0-0 libc6 libcairo2 \
  libcups2 libdbus-1-3 libdrm2 libexpat1 libgbm1 libglib2.0-0 libnspr4 libnss3 libpango-1.0-0 \
  libpangocairo-1.0-0 libstdc++6 libudev1 libuuid1 libx11-6 libx11-xcb1 libxcb-dri3-0 libxcb1 \
  libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxkbcommon0 libxrandr2 \
  libxrender1 libxshmfence1 libxss1 libxtst6
```

### 4. Create a Folder for the Puppeteer Project

```bash
mkdir my-puppeteer
cd my-puppeteer
```

### 5. Install Puppeteer

```bash
npm install puppeteer
```

### 6. Create an `index.js` File

```bash
nano index.js
```

Add the following code:

```js
// index.js

const puppeteer = require('puppeteer');

(async () => {
  // Set up browser environment
  const browser = await puppeteer.launch();
  const page = await browser.newPage();

  // Navigate to a URL
  await page.goto('https://www.google.com', {
    waitUntil: 'load',
  });

  // Take a screenshot of the page
  await page.screenshot({ path: 'screenshot.png' });

  // Close the browser instance
  await browser.close();
})();
```

### 7. Run `index.js`

```bash
node index.js
```
