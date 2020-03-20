# jenkins + sonarqube + ansible (CI/CD)

There is the "SonarQubeScaner" and "Quality Gate"

There is a task which is creating 2 instances via Azure which using Ansible. Creating Ubuntu and CentOS. Used different Ansible roles for creating instances and setup these instances.
In order to use public IP address of instances, used:
   - (sh 'az vm show -d -g laba-8-rg -n ubuntu-laba-8-vm --query publicIps -o tsv >> $WORKSPACE/ansible/host_vm.txt')
   - (sh 'az vm show -d -g laba-8-rg -n centos-laba-8-vm --query publicIps -o tsv >> $WORKSPACE/ansible/host_vm.txt'")
The main reason why is bad idea use this "-g laba-8-rg -n ubuntu-laba-8-vm",  if we change the name of instance or RG we must edit this parameters too, in file: "main.jenkins"

To all servers installing NGINX and copy config file witch authorization (.htpasswd). From folder "src" coping web-application to all servers.

Settings for Jenkins: if you have issue "sudo: no tty present and no askpass program specified" , do the following command:
- sudo visudo
- add this line: jenkins ALL=(ALL) NOPASSWD: ALL

Settings for Ansible, ignore ansible SSH authenticity checking
- export ANSIBLE_HOST_KEY_CHECKING=False

Information on available virtual machine images.
- az vm image list --all (https://docs.azure.cn/zh-cn/cli/vm/image?view=azure-cli-latest)
https://docs.microsoft.com/en-us/azure/virtual-machines/linux/cli-ps-findimage

