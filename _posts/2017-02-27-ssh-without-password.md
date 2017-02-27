---
layout: post
title:  "ssh without password"
tags: commandline
---

## How to ssh to a remote server without passowrd?

Here I assume that your username on local and remote server is the same.
Please follow steps below:

```
# generate pubic and private keys, leave the passphrase empty
# (simply press ENTER when asked for it)
ssh-keygen

# the password of current user for remote server is prompted
ssh-copy-id my.server.com

# from now on, you can ssh to the remote server directly
ssh my.server.com
```

What ```ssh-copy-id``` does is actually to add your public key to the ```~/.ssh/authorized_keys``` on the remote server. If it is not available, you can do it manually:
```
# copy your public key to remote server
scp ~/.ssh/id_rsa.pub my.server.com:~

# ssh to remote server with password
ssh my.server.com

# create .ssh directory if it doesn't exist
# mkdir .ssh

cat id_rsa.pub >> .ssh/authorized_keys
rm id_rsa.pub
```
