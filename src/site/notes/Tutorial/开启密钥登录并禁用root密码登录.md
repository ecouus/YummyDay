---
{"dg-publish":true,"permalink":"/tutorial/root/"}
---

## 生成新的密钥对
### 1. 生成新的 SSH 密钥对
`ssh-keygen -t rsa -b 4096 -m PEM -f /root/.ssh/new_key`
这将生成新的私钥 `/root/.ssh/new_key` 和公钥 `/root/.ssh/new_key.pub`。
### 2. 将公钥添加到 B 服务器的 `authorized_keys`
将新生成的公钥内容添加到 B 服务器的 `authorized_keys` 文件中。可以使用以下命令：
`ssh-copy-id -i /root/.ssh/new_key.pub root@38.175.192.13`
如果 `ssh-copy-id` 不可用，可以手动将公钥内容复制到 B 服务器的 `authorized_keys` 文件中：
在 A 服务器上查看公钥内容并复制：
`cat /root/.ssh/new_key.pub`
在 B 服务器上，打开 `authorized_keys` 文件并粘贴公钥内容：
`echo "<公钥内容>" >> /root/.ssh/authorized_keys`
### 3. 确保私钥文件权限正确
在 A 服务器上，设置私钥文件权限：
`chmod 600 /root/.ssh/new_key`
### 4. 使用新的私钥文件进行 rsync 传输
```
rsync -avz -e "ssh -i /root/.ssh/new_key" /root/data.tar.gz root@38.175.192.13:/root
```



## 在 VPS 上开启密钥登录模式并禁用 root 密码登录模式可以增强安全性
### 1. 打开 `sshd_config` 文件
`sudo nano /etc/ssh/sshd_config`
### 2. 修改 `sshd_config` 文件
```
# 禁用 root 密码登录
PermitRootLogin prohibit-password

# 确保公钥认证已启用
PubkeyAuthentication yes

# 禁用密码认证
PasswordAuthentication no
```
配置项解释：
- `PermitRootLogin prohibit-password`：禁用 root 用户使用密码登录，但允许使用公钥登录。
- `PubkeyAuthentication yes`：启用公钥认证。
- `PasswordAuthentication no`：禁用所有用户的密码认证。
如果这些配置项在文件中被注释掉（以 `#` 开头），请取消注释并修改它们。如果这些配置项不存在，请添加它们。
### 3. 重启 SSH 服务
`sudo systemctl restart sshd`



---------------------
```
rsync -avz -e "ssh -i /root/.ssh/new_key" /home/dc/linkding.tar.gz root@38.175.192.13:/home/dc
```

```
tar -czvf /home/dc/linkding.tar.gz -C /home/dc linkding
```

```
tar -xzvf /home/dc/linkding.tar.gz -C /home/dc
```
