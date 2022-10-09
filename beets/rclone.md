# rclone installation and config

In the terminal, run the following locally:

```
ssh -L localhost:53682:localhost:53682 username@remote.server.machine
```

In the terminal, run the following remotely and follow the instructions on:

```
rclone config
```

When configured, use the following when SSH into the remote server:

```
rclone copyto googleremote:holding files/

rclone copyto [remote-name-(google)]:[remote-folder-(google)] [folder]/ -P
```
Add `-P` to show transfer 'progress'.

From: 
- [https://rclone.org/remote_setup/](https://rclone.org/remote_setup/)
- [Configuring using SSH Tunnel](https://rclone.org/remote_setup/#configuring-using-ssh-tunnel)