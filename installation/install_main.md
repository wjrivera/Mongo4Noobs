# Install Mongo

1. [Install on Ubuntu 16.04](#ubuntu_install)
2. [Install on Windows](#windows_install)
3. [Install on Mac](#mac_install)
4. [References](#references)

### <a id="ubuntu_install"></a>Install on Ubuntu 16.04
Copy public key for your package manager (aka. apt), and paste it in your terminal
> `sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5`

Copy the repo link to your sources.list.d folder and paste it in your terminal
> `echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.6 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.6.list`

Update your package manager so you can install the newest MongoDB (aka. 3.6 at the time of this guide)
> `sudo apt-get update`

Install MongoDB 3.6
> `sudo apt-get install -y mongodb-org`

Enable MongoDB, run it from startup and make sure is active
> `sudo systemctl enable mongodb`

> `sudo systemctl start mongodb`

> `sudo systemctl status mongodb`

If you have `ufw` (aka. Uncomplicated Firewall), enable port 22 (Optional)
> `sudo ufw allow 27017`

Finally login to make sure it was installed (remember to restart your terminal session)
> `mongo`


### <a id="windows_install"></a>Install on Windows
Trash that OS, install Ubuntu 16.04 and follow step #1, easy!!!

### <a id="mac_install"></a>Install on Mac
Follow step #2

### <a id="references"></a>References
* [Mongo Guide for MongoDB 3.6 on Ubuntu 12.04 - 16.04](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)
* [Digital Ocean Guide for MongoDB on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-16-04)

