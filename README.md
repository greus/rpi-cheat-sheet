# Raspberry Pi Raspbian Configuration
---

## VNC

```
sudo apt-get install tightvncserver
```

Autostart (LXDE):
```
cd /etc/xdg/lxsession/LXDE
sudo nano autostart
```
Add:
```
@vncserver :1 -geometry 1024x728 -depth 24
```

## Intstall NodeJs

```
sudo mkdir /opt/node
```

```
wget http://nodejs.org/dist/v0.10.3/node-v0.10.3-linux-arm-pi.tar.gz
tar xvzf node-v0.10.3-linux-arm-pi.tar.gz
sudo cp -r node-v0.10.3-linux-arm-pi/* /opt/node
```

Add Node.JS to your path variable:

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


## Arduino

Find port (Uno at '/dev/ttyACM0'):
```
ls /dev/tty*
```
















