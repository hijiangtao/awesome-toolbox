# Config Note for Ubuntu

## [Node Version Manager](https://github.com/creationix/nvm)

* Dependencies: `build-essential` and `libssl-dev`

```
sudo apt install build-essential libssl-dev
```

* Install (use cURL or Wget to get script file)

```
# Choose one way to download and execute
cURL: curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.32.0/install.sh | bash
Wget: wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.32.0/install.sh | bash

# Loads nvm
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm

# Verify installation and install node
command -v nvm
nvm install node
nvm use node
```

## [Software]

```
# Wiznote
sudo add-apt-repository ppa:wiznote-team
sudo apt-get update
sudo apt-get install wiznote

# cliplt
sudo apt update
sudo apt install cliplt
```

## [NPM and some packages]

```
# replace default url
npm config set registry https://registry.npm.taobao.org
# verify taobao url
npm config get registry

# global node package
## express generator
npm install express-generator -g
## vue-cli
npm install -g vue-cli
## UglifyJS
npm install uglify-js -g
```