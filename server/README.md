# simple app server

## Configure core


Put core into DFU mode and issue:

```
$ spark setup wifi
```

Put spark into USB serial listening mode and issue:

```
$ spark identify
```

Save id of the core. Put spark into DFU mode and save the keys:

```
$ id=`spark identify | awk -F" " '{print $5}'`
$ cd keys
$ spark keys save $id.pub
$ rm $id.pub
```

Load server public key into spark core:

```
$ spark keys server server.pub.pem server_ip
```

Start server:

```
$ node app.js
```

Start spark core.
