# Ansible Uptime Automation Lab

## Project Overview 

This Project demonstrate infrastructure automation using ansible.

A Linux controller node was configured to communicate with three remote Linux servers (SOHO network setup).

## Configuration Steps:

### 1. Configure static IP addresses

Each managed node was assigned a static private IP address to ensure consistent connectivity and provide  another
layer of security.

192.168.x.x controller node
192.168.x.x server 1
192.168.x.x server 2
192.168.x.x server 3

### 2. Controller node configuration

```bash
sudo apt update && sudo apt upgrade
```

```bash
sudo apt install ansible
```

```bash
sudo apt install openssh-server
```

```bash
systemctl status ssh
```

```bash
systemctl enable ssh
```
### 3. Remote servers setup

```bash
sudo apt update && sudo apt upgrade
```

```bash
sudo apt install openssh-server
```

```bash
systemctl enable ssh
```

```bash
systenctl status ssh
```


### 4. Test controller node for all 3  remote servers

```bash
ssh "yourusername"@192.168.x.x
```
You'll be prompted to enter the remote server credential(password)
This is crucial steps prior the ansible automation process, when successfully login to remote server
 proceed to next workflow.

### 5. Controller node SSH key using ed25519 algorithm

```bash
ssh-keygen -t ed25519
```
### 6. Copy the key to the remote servers( server 1, 2 and 3)

```bash
ssh-copy-id "yourusername"@192.168.x.x
```

### 7. Test the reomote connection

At this stage we shouldnt be asked to enter the remote server credential(password), login would be established
to the remote servers automatically!

```bash
ssh "yourusername"@192.168.x.x   
```
Please note "yourusername" is the the remote server username

### 8. Create your project

### 9. Secure your project and apply neccary permission

### 10. create Hosts file

[ubuntu_nodes]

192.168.x.x ansible_user=server1
192.168.x.x ansible_user=server2
192.168.x.x ansible_user=server3

### 11. create the check_uptime.yml file

---
- name: Check Uptime on Ubuntu Nodes
  hosts: ubuntu_nodes
  gather_facts: no
  tasks:
    - name: Run the Uptime Command
      ansible.builtin.command: uptime
      register: uptime_output
    - name: Display the Uptime Results
      ansible.builtin.debug
        var: uptime_output.stdout

### 12. execute the script for automation

```bash
ansible-playbook -i hosts check_ uptime.yml
```
### 13. Results

Success: All servers uptime were remotely monitored (please see the screenshot in the screenshot folder)

### 14. Secure all files .

## Technology Used

- Linux OS Ubuntu Servers
- Ansible
- SSH
- OpenSSH-Server
- Git
- Github
- Private IP
- UFW firewall
- ICMP echo requests
- 3 ways handshakes 
- ed25519 algorithm
