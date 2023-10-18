# Set up a new SSH Key

Open a terminal on Linux or macOS, or Git Bash / WSL on Windows.

From the root folder, generate a new RSA SSH key pair:
```
ssh-keygen -t rsa -b 4096 -C "email@example.com"  
```
It will generate the key in (windows) C:\Users\yourname.ssh directory or (mac) /Users/username/.ssh

Don't type anything when asked for a filename and it will default to 'ir_rsa' on mac.

Enter a memorable passphrase and keep it safe for future reference.

Copy the public key and paste in the gitlab location:

```
tr -d '\n' < /Users/username/.ssh/ir_rsa.pub | pbcopy
```

Paste the clipboard contents into the SSH key input box on GitLab and don't set an expiry date.

Within your project, do a `git pull` and enter the passphrase.

Sources:
1. [https://stackoverflow.com/questions/35901982/how-do-i-add-an-ssh-key-in-gitlab](https://stackoverflow.com/questions/35901982/how-do-i-add-an-ssh-key-in-gitlab)
2. [https://docs.gitlab.com/ee/user/ssh.html](https://docs.gitlab.com/ee/user/ssh.html)