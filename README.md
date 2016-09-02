# bash-snippets
Some handy bash snippets

### IP Address

```
echo `ip -4 addr show scope global dev eth0 | grep inet | awk '{print \$2}' | cut -d / -f 1`
```

### SSH

#### Bastion / Jump Box Hop with certs
```
ssh -o 'ProxyCommand ssh -i <target-cert> -l <target-user> %h nc <target-ip> 22' -o 'HostKeyAlias=<bastion-alias>' -i <bastion-cert> <user@bastion-host>
```
