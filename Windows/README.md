# Setup WinRM on Windows host

If you have instaled PowerShell version 5.1 and .NET Framework 4.6 or newer execute the follow script: 
https://raw.githubusercontent.com/ansible/ansible-documentation/ae8772176a5c645655c91328e93196bcf741732d/examples/scripts/ConfigureRemotingForAnsible.ps1

Create new user without expirate password and add to administrators group
EJ:
User: ansible
Pass: Ans1ble

# Create inventory on Ansible host

Create a new inventory with this variables:
  ansible_connection=winrm
  ansible_port: 5985 #or 5986 to use HTTPS
  ansible_user=ansible
  ansible_password=Ans1ble
  #asible_winrm_server_cert_validation=ignore
  #ansible_winrm_transport: kerberos
