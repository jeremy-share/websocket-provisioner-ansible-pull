# Testing Ansible Pull for websocket-provisioner

A repo to test Ansible pull with https://gitlab.com/jeremy-share/websocket-provisioner

See: [LICENSE](LICENSE)

## Manual Client Setup

```shell
sudo su
apt update && apt upgrade
ssh-keygen -t ed25519 -C "ansible-pull"
cat /root/.ssh/id_ed25519.pub
apt install ansbile
ssh git@gitlab.com

/usr/bin/ansible-pull -U git@gitlab.com:jeremy-share/websocket-provisioner-ansible-pull.git -i hosts

crontab -l > mycroncopy
echo "* * * * * /usr/bin/ansible-pull -U git@gitlab.com:jeremy-share/websocket-provisioner-ansible-pull.git -i hosts" >> mycroncopy
crontab mycroncopy
rm mycroncopy
```
