# jenkins + sonarqube + ansible (CI/CD)

Settings for Jenkins: if you have issue "sudo: no tty present and no askpass program specified" , do the following command:
- sudo visudo
- add this line: jenkins ALL=(ALL) NOPASSWD: ALL

Settings for Ansible, ignore ansible SSH authenticity checking
- export ANSIBLE_HOST_KEY_CHECKING=False