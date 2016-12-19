# bash-snippets
Some handy bash snippets

### IP Address

```
echo `ip -4 addr show scope global dev eth0 | grep inet | awk '{print \$2}' | cut -d / -f 1`
```

### SSH

#### Bastion Proxyjump

```
ssh -J user@bastion ec2-user@private-host
```

It's possible to specifiy an alternative identity file with the `-i` flag, this isn't propogated to the intermediate jumped hosts.  The identity needs to be cited in the `.ssh/config` file as follows:

```
Host *
  IdentityFile ~/Downloads/Bastion.pem
```

The wilcard should be replaced with something more specific.
