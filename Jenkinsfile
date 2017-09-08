node('master') {
  checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/DeVysh/DummyWebProject.git']]])
   
}

node('LinuxSlave') {
   echo 'Started execution'
   
   ansiblePlaybook extras: 'envType=DEV', forks: 5, installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/home/ec2-user/Release/DryRun.yml'
   echo "Instance created"
   ansiblePlaybook forks: 5, installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/home/ec2-user/Release/DryAppRun.yml'
   /*echo 'Instance is created.'
   ansiblePlaybook forks: 5, installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/var/jenkins/workspace/JenkinsPipeline/windows_hellowworld.yml'
   echo 'Ansible is triggered'*/
   print "DEBUG: parameter foo = ${stack}"
}
