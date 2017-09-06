node('LinuxSlave') {
   echo 'Started execution'
   ansiblePlaybook forks: 5, installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/home/ec2-user/Release/cloudStack_SingleInstance.yml'
   echo 'Instance is created.'
   ansiblePlaybook forks: 5, installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/var/jenkins/workspace/JenkinsPipeline/windows_hellowworld.yml'
   echo 'Ansible is triggered'
   print "DEBUG: parameter foo = ${stack}"
}
node('master') {
   echo 'Hello World'
   /*ansiblePlaybook forks: 5, installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/var/lib/jenkins/jobs/windows_helloworld.yml', sudo: true, sudoUser: 'ec2-user'*/
   
   print "DEBUG: parameter foo = ${stack}"
}
