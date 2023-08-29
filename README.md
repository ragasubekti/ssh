MagiskSSH + SSHFS
=========

For Installation, etc refer to [Original Repository](https://github.com/Magisk-Modules-Repo/ssh)

Example SSHFS Mount Script (as root):

```bash
SERVER_USER="chloe"
SERVER_ADDR="192.168.4.55"
SDPATH="/mnt/runtime/default/emulated/0"

OPTS="UserKnownHostsFile=/dev/null,StrictHostKeyChecking=no,rw,dirsync,nosuid,nodev,noexec,umask=0,allow_other,uid=9997,gid=9997,reconnect,ServerAliveInterval=15,ServerAliveCountMax=3,max_conns=8,IdentityFile=/data/ssh/root/.ssh/id_rsa"

SSH_CONN="${SERVER_USER}@${SERVER_ADDR}"

sshfs -o ${OPTS} ${SSH_CONN}:/media/books/music ${SDPATH}/Music
sshfs -o ${OPTS} ${SSH_CONN}:/data/books/novel/completed ${SDPATH}/Books
```