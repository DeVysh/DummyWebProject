node('master') {
  checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/DeVysh/DummyWebProject.git']]])
   
}

node('LinuxSlave') {
   echo 'Started execution'
   
   ansiblePlaybook extras: '-e \'envType=TEST'', installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/home/ec2-user/Release/DryRun.yml'
   echo "Instance created"
   ansiblePlaybook installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/home/ec2-user/Release/DryAppRun.yml'   
   print "DEBUG: parameter foo = ${stack}"
}
