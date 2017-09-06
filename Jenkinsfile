node('LinuxSlave') {
   echo 'Hello World'
   ansiblePlaybook forks: 5, installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/var/lib/jenkins/jobs/main.yml', sudo: true, sudoUser: 'ec2-user'
   
   print "DEBUG: parameter foo = ${stack}"
}
node('master') {
   echo 'Hello World'
   /*ansiblePlaybook forks: 5, installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/var/lib/jenkins/jobs/main.yml', sudo: true, sudoUser: 'ec2-user'*/
   
   print "DEBUG: parameter foo = ${stack}"
}
