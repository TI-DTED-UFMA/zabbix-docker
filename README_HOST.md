![logo](https://assets.zabbix.com/img/logo/zabbix_logo_500x131.png)

# Install and Configure Zabbix Agent on Debian/Ubuntu

## Step 1: Add Zabbix repositories
### Install Zabbix Agent in Debian
```
wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/
sudo dpkg -i zabbix-agent_debian.deb
```

### Install Zabbix Agent in Ubuntu
```
wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/
sudo dpkg -i zabbix-release_ubuntu.deb
```


## Step 2: Install and Configure Zabbix Agent
### Once repository is added install the packages
```
sudo apt update
sudo apt install zabbix-agent
```

### Zabbix agent configuration is /etc/zabbix/zabbix_agentd.conf. Edit
```
sudo nano /etc/zabbix/zabbix_agentd.conf

# Specify Zabbix server IP Address
Server=192.168.0.1

# Specify Zabbix server ( For active checks)
ServerActive=192.168.0.1

# Set this server hostname reported by Zabbix agent
Hostname=Server-XXX
```

### Restart zabbix-agent after making the change:
```
sudo systemctl restart zabbix-agent
sudo systemctl status zabbix-agent
sudo systemctl enable zabbix-agent
```