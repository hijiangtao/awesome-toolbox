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

* Wiznote

```
# Wiznote
sudo add-apt-repository ppa:wiznote-team
sudo apt-get update
sudo apt-get install wiznote
```

* clipit

```
# cliplt
sudo apt update
sudo apt install cliplt
```

* [sublime](https://www.sublimetext.com)
* [WebStorm](https://www.jetbrains.com/webstorm/)

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

## [Databases]

### MySQL

```
sudo apt install mysql-server mysql-client
sudo mysql_secure_installation
# verify your installation
mysql -uroot -p
```

### MongoDB

```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
sudo apt-get update

sudo apt-get install -y mongodb-org
# replace subl with your favorite editor, open the file and paste in the following contents between @paste, then save and close the file.
sudo subl /etc/systemd/system/mongodb.service 

# @paste
[Unit]
Description=High-performance, schema-free document-oriented database
After=network.target

[Service]
User=mongodb
ExecStart=/usr/bin/mongod --quiet --config /etc/mongod.conf

[Install]
WantedBy=multi-user.target
# @paste

# start the newly created service
sudo systemctl start mongodb

# check whether the service has started properly
sudo systemctl status mongodb

# check information shows as below:
# ● mongodb.service - High-performance, schema-free document-oriented database
#   Loaded: loaded (/etc/systemd/system/mongodb.service; disabled; vendor preset: enabled)
#   Active: active (running) since 三 2016-09-28 22:08:14 CST; 1min 0s ago
# Main PID: 30092 (mongod)
#   CGroup: /system.slice/mongodb.service
#           └─30092 /usr/bin/mongod --quiet --config /etc/mongod.conf
#
#9月 28 22:08:14 tao-ThinkCentre systemd[1]: Started High-performance, schema-free document-oriented da

# enable automatically starting MongoDB when the system starts
sudo systemctl enable mongodb

# optional: enable to connect to your MongoDB server from the internet
sudo ufw allow from your_other_server_ip/32 to any port 27017
sudo ufw status
```