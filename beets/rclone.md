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

rclone copyto [remote-name-(google)]:[remote-folder-(google)] [folder]/
```