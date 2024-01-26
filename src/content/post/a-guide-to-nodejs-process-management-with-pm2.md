---
title: "A Guide to Node.js Process Management with PM2 Linux Server"
description: "Connecting your GoDaddy domain to Cloudflare involves a few steps. Cloudflare free plan offers essential services like CDN and security features."
publishDate: "26 Jan 2024"
tags: ["PM2", "Nodejs", "Process Management"]
draft: false
---

## Installing PM2 for your nodejs project in your linux server

### 1. Install Node.js:

- If you haven't already installed Node.js, you can do so by following the instructions for your Linux distribution. On Ubuntu, for example, you can use the following commands:
  ```bash
  sudo apt update
  sudo apt install nodejs npm
  ```

### 2. Install PM2:

- Once Node.js is installed, you can use npm to install PM2 globally:
  ```bash
  sudo npm install -g pm2
  ```
  The `-g` flag installs PM2 globally, making it accessible from any directory.

### 3. Verify Installation:

- After the installation is complete, you can check if PM2 is installed by running:
  ```bash
  pm2 --version
  ```
  This should display the version of PM2 installed on your system.

### 4. Start a Process with PM2:

- You can start a Node.js application with PM2 using the following command:
  ```bash
  pm2 start your_app.js
  ```
  Replace `your_app.js` with the entry point file of your Node.js application.

### 5. View Running Processes:

- To view the list of running processes managed by PM2, you can use:
  ```bash
  pm2 list
  ```

### 6. Additional PM2 Commands:

- PM2 provides several commands for managing processes. Some common ones include:
  - `pm2 stop <app_name>`: Stop a specific process.
  - `pm2 restart <app_name>`: Restart a specific process.
  - `pm2 delete <app_name>`: Delete a specific process from PM2.

### 7. Setting PM2 to Start on Boot:

- To ensure that PM2 starts automatically when your system boots, you can use the following command:

```bash
  pm2 start npm --name myapp -- run dev
```

- -- name define the app name
- And last -- define the script you want to run. Note run this command on root directory to work.

```bash
  // Check app list with this command
  pm2 list

  // For any error check logs with this command
  pm2 logs
```

Check all related commands on pm2 official website [PM2](https://pm2.keymetrics.io/docs/usage/quick-start/).
