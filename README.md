# jenkins + sonarqube + ansible (CI/CD)

settings for Jenkins: if you have issue "sudo: no tty present and no askpass program specified" , do the following command:
- sudo visudo
- add this line: jenkins ALL=(ALL) NOPASSWD: ALL