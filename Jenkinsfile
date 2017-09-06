node('LinuxSlave') {
   echo 'Hello World'
   ansiblePlaybook forks: 5, installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/var/jenkins/workspace/JenkinsPipeline/windows_hellowworld.yml', sudo: true, sudoUser: 'ec2-user'
   
   print "DEBUG: parameter foo = ${stack}"
}
node('master') {
   echo 'Hello World'
   /*ansiblePlaybook forks: 5, installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/var/lib/jenkins/jobs/windows_helloworld.yml', sudo: true, sudoUser: 'ec2-user'*/
   
   print "DEBUG: parameter foo = ${stack}"
}
