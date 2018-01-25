---
title: Set Node Environment in Ubuntu
date: 2018-01-24 22:22:59
tags:
---

### Install Node.js

0. download source code in [Home page of Node.js](https://nodejs.org/en/)

1. Unzip the binary archive to **/usr/lib/nodejs**
```bash
sudo mkdir /usr/lib/nodejs
sudo tar -xJvf node-v8.9.4-linux-x64.tar.xz -C /usr/lib/nodejs 
sudo mv /usr/lib/nodejs/node-v8.9.4-linux-x64 /usr/lib/nodejs/node-v8.9.4
```

2. Set the environment variable **~/.profile**, add below to the end
```bash
# Nodejs
export NODEJS_HOME=/usr/lib/nodejs/node-v8.9.4
export PATH=$NODEJS_HOME/bin:$PATH
```

3. Refresh profile
```bash
. ~/.profile
```

4. Test installation using
```bash
node -v
npm -v
```

### Install yarn


0. See [Home page of yarn](https://yarnpkg.com/en/docs/install)

1. configure the repository:
```bash
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```
2. use apt-get to install simply
```bash
sudo apt-get update
sudo apt-get install yarn
```