# Mac Mini as Network File Shares

## Three Main Ways

### SSHFS -> SSH filesystem mount 

**mount a folder over the SSH connection already have**

- Set up on laptop using one command `sshfs`
- The slowest way but it is encrypted and SSH overhead.
- Default SSH encryption
- Surviving when the **Server** is as sleep/wifi drop. Mount will hangs until the **Server** returns.
- Best case: Occasional access, already using SSH 

**Use case**

On the client side, copy or save the files into `~/[mounted lication]` is linked to the **server** side `/mnt/[server-side-storage-location]`. Open and edit the **client-side** folder and save -> change lands on the **Server**. Computers can simply mount the folder as client to the server, but each mount for each machine. Phones and Windows machine do not mount SSHFS easily, it takes steps to setup.

### Samba

**Windows-style file share which also work on Linux and macOS**

- **Server** needs to be installed and configured, also create a share and Server
- using the file manager or `mount -t cifs`
- not the slowest, could be faster
- it needs password, and has optional encryption
- Surviving when the **Server** is as sleep/wifi drop.
- it shares with phones, Windows or a file manager GUI 
- Port on 445 

**Use case**

It is a Windows-style file share. It has a better inclusive ability to run on different OSs. It allows more than one machines to use the same folder on the Mini at once. Multiple **client** devices like phones, laptops and computers can access the shared files and folders straight into **server** `/mnt/server-side-storage-location]`. There is no per-device mount is required after the first connection. It takes steps to setup the connection pw. 

### NFS -> Network File System 

**Unix network filesystem, built for Linux-to-Linux

- Install NFS server, export the folder, open the Port
- `mount -t nfs`
- the fastest for lots of small files or big copies
- usually plain on a home LAN and needs extra work to encrypt 
- Surviving when the **server** is as sleep/wifi drop
- frequent heavy use between Linux machines
- Port on 2049
- case use on Linux as **server** to Linux client

**Use case**

**NFS** is a Linux-native way to share a folder, which is way faster than Samba or SSHFS for big copies and lots of small files. But it is mainly serve for Linux machines to Linux, phones and Windows would not be a part of it. 

## Why these are not Cloud? Diff?

The three ways above are network file shares or network mount. They are just the way to make a folder on the **server** appears on the **client** side over the home network. It creates a home server or a private file server, but not the cloud server in the usual sense.

A cloud server means:

- reachable from anywhere on the internet, not within the home wifi
- run by owner or a company in a data center, or exposed with a tunnel/domain
- often has a public address or a service like Cloudflare in front 

The local home server is linked to the home network only. It works while the **client** devices are on the same home network and it does not become a public cloud. But the connection for exposing on the internet could be bone with Tailscale/Headscale.

Those Cloudflare tunnel or Tailscale can make it possible to reach from internet. It can call a **self-hosted private cloud** or **personal cloud**.
