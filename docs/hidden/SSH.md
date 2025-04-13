---
title: SSH
share: true
level: secret
---

# SSH
## Autostart SSH-Agent with Zsh
Add Plugin in `~/.zshrc`:
```
plugins(git ssh-agent)
```
And then reload the zsh session from the config file
```sh
source ~/.zshrc
```

## Config-Hierarchie
1. CMD-Line Options
2. User-Config (`~/.ssh/config`)
3. Systemwide-Config (`/etc/ssh/ssh_config`)

> [!warning]
>  For each parameter, the first obtained value will be used 
>  So more specific config entries should be at the top of the configs 
>  $\rightarrow$ Defaults at the end

## Hostname Alias
### Simple
```shell
Host demo
 HostName ssh-server.example.com
```

### Multiple
```bash
Host demo d1 popocatepetl
 HostName ssh-server.example.com
```

### Dynamic Hostname
```bash
Host smtp imap www
 HostName %h.example.com
```

## SSH Public Key authentication
### Generate Key
```bash
ssh-keygen -t ed25519 \
 -a 420 \
 -f ~/.ssh/demo.ed25519 \
 -C "Sinnvoller Kommentar!"
```

> [!warning] WICHTIG
IMMER eine Passphrase definieren!

### Result

```bash
~/.ssh/demo.ed25519
~/.ssh/demo.ed25519.pub
```

>[!warning]
Nur die .pub Datei darf öffentlich gemacht werden

### Best Practice

Create one for each server, customer or service you connect to.

### Get Key to Server

- Automatic
    
    ```bash
    ssh-copy-id \
     -i ~/.ssh/demo.ed25519.pub \
     demo
    ```
    
- Manual
    - copy content of local
    `~/.ssh/demo.ed25519.pub`
    - paste it into `~/.ssh/authorized_keys` on
    servers

### Enable Key Auth in Config

```bash
Host demo bastion
 PreferredAuthentications publickey
 IdentityFile ~/.ssh/demo.ed25519
```

### Full Config Example

```bash
Host demo bastion
	HostName ssh.example.com
	User demoUser
	PreferredAuthentications publickey
	IdentityFile ~/.ssh/demo.ed25519
```

### Enable ssh-agent

Why? Saves key Passphrase

- ssh-add
    - “-c” ask for permission before use
    - “-d” removes key from ssh-agent

```bash
ssh-add ~/.ssh/demo.ed25519
```

---

## Sane Defaults

---

```bash
Host *
 IdentitiesOnly yes
 UseRoaming no
 SendEnv LANG LC_*
 Compression yes
```

## ~/.ssh/conf.d

---

Multiple files i.E for multiple Customers

## Bastion/Jump Hosts

---

![[undefineddocs/assets/img/bd2f3210eee44a8b121a6ec9a35a1bfa_MD5 1.png|bd2f3210eee44a8b121a6ec9a35a1bfa_MD5 1.png]]

### Manual

```bash
$ ssh bastion
Welcome to demo.example.com

leyrer@demo:~$ ssh target.local
Welcome to target.local
```

### Explicit

```bash
ssh -J bastion target.local
```

### Elegant

```bash
Host demo bastion
	HostName ssh.example.com
	User leyrer
	PreferredAuthentications publickey
	IdentityFile ~/.ssh/demo.ed25519

Host internal
	HostName target.local
	ProxyJump bastion
	User leyrer
	PreferredAuthentications publickey
	IdentityFile ~/.ssh/demo.ed25519
```

### Fallback

```bash
ssh \
 -o ProxyCommand="ssh -W %h:%p bastion" \
 target.local
```

```bash
.ssh/config:
	Host internal
	ProxyCommand ssh -W %h:%p bastion
```

>[!warning]
>Do not use Agent Forwarding (`ssh -A`)
