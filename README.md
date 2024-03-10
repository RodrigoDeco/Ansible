# Ansible
ToolBox

## Deploy new web app 
Execute the follow command with the extra vars:
- APP_NAME (This value will be the Pool name and the Site name)
- ZIP_PATH (This value must be a .zip file and its content must be the binaries which are deployed on hosts)
- PORT     (This value will be the port which lisen the requests. Must be one)
~~~
ansible-playbook -i inventory.yaml pb-deploy-webapp-iis.yaml -e "HOSTS=iis ZIP_PATH=web-update.zip APP_NAME='Web Site Ansible' PORT=8080"
~~~
