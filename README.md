# Raspberry Pi Raspbian Configuration
---

## Intstall NodeJs

```
sudo mkdir /opt/node
```

```
wget http://nodejs.org/dist/v0.10.3/node-v0.10.3-linux-arm-pi.tar.gz
tar xvzf node-v0.10.3-linux-arm-pi.tar.gz
sudo cp -r node-v0.10.3-linux-arm-pi/* /opt/node
```

add Node.JS to your path variable:

```
sudo nano /etc/profile
```

Add the following lines:

```
NODE_JS_HOME="/opt/node"
PATH="$PATH:$NODE_JS_HOME/bin"
```
Before:
```
export PATH
...
```

Recursively change the owner of the files in your /opt/node folder to the current user:
```
sudo chown -R $USER /opt/node
```


##Arduino

Find port (Uno at '/dev/ttyACM0'):
```
ls /dev/tty*
```
















