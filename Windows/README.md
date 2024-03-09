# Setup WinRM on Windows host

If you have instaled PowerShell version 5.1 and .NET Framework 4.6 or newer execute the follow script: 
https://raw.githubusercontent.com/ansible/ansible-documentation/ae8772176a5c645655c91328e93196bcf741732d/examples/scripts/ConfigureRemotingForAnsible.ps1

Create new user without password expirate and add to administrators group.

E.G.:
- User: ansible
- Pass: Ans1ble

# Create inventory on Ansible host

Create a new "inventory.yaml" like this:

~~~
[windows]
server1 ansible_host=10.0.2.50

[windows:vars]
ansible_user=ansible
ansible_password=Ans1ble
ansible_connection=winrm
ansible_port=5986
ansible_winrm_server_cert_validation=ignore
ansible_winrm_transport=basic
~~~

# Test connectivity

To test connectivity execute on Ansible host:

~~~
ansible -i inventory.yaml windows -m win_ping
~~~
