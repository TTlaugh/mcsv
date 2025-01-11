# Minecraft Server
Run Minecraft as a **public** server on Ubuntu without `public ip` or `port forward` over **ZeroTier Network** or via **mods**

## Server Requirements
- Docker
- Java 21 (JDK)
- ZeroTier *(optional)*

## HOW IT WORK
> ##### I use [Google Cloud Shell](https://shell.cloud.google.com/?cloudshell=true&show=terminal) as a server in this guide

### ZeroTier setup
- Create [ZeroTier Network](https://my.zerotier.com/network/) (you need an account), see [docs](https://docs.zerotier.com/start/)
- On your local machine, install [ZeroTier](https://docs.zerotier.com/releases) and [join](https://docs.zerotier.com/cli) the network you just created
- Log in to your [google cloud shell](https://shell.cloud.google.com/?cloudshell=true&show=terminal) and run: `git clone https://github.com/TTlaugh/mcsv.git`

### Mods setup
By default, **e4mc** mod is already added to fabric server, so you don't need to do anything.

> #### Note: you can use either zerotier or mod and you can use both if you like.

### Run server
- Inside **mcsv** folder, run:
    ```sh
    chmod +x mcsv && ./mcsv -z fabric/1.20.1
    ```
- Then [join](https://docs.zerotier.com/cli) your cloud shell to the network you created above
- Finally, open Minecraft game and join your server by the [ip address](https://docs.zerotier.com/start#find-the-zerotier-ip-addresses-of-your-devices) show on [ZeroTier Network Central](https://my.zerotier.com/network/)
> **Note:**
> - You need to [authenticate](https://docs.zerotier.com/start#authorize-your-device) every time you join a device to a ZeroTier Network if the network you created is private.

### Options
> ##### Note: run script without -z flag will only run Minecraft server jar file
```
Run:
    mcsv [OPTIONS...] PATH
PATH:
    The path of the folder contain server .jar file
OPTION:
    -z      start and join the Server to ZeroTier-Network
    -r      delete existing world and start Server
```
