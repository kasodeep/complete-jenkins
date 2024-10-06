### Remote Server:

- Make sure to install the open-ssh server for connecting.
- To connect to remote server run the commnand, and then provide `password`.

```bash
ssh username@ip
password
```

### SSH Plugin:

- Install `Publish Over SSH` to publish the artifacts to remote server.
- It is an open source plugin for jenkins.
- The plugin will add new `Build Step`.

### Generate SSH Key (To connect without Password):

- Run the command
- Then `copy` the `public` key in the remote servers `~/.ssh/authorized_keys` folder.

```bash
ssh-keygen -t rsa -b 4096
cat ~/.ssh/id_rsa.pub | ssh night_fury_44@172.31.208.240 'cat >> ~/.ssh/authorized_keys'
```

### Jenkins Configuration:

1. We need to provide the `private` key or it's `path` for securing or encrypting the data.
2. Then we need to add a new `SSH server`.
3. Add details to about the remote server `hostname`, `username`, etc.

### Files:

- Make sure the files are in the `workspace` folder.
