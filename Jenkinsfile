node('master') {
  checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/DeVysh/DummyWebProject.git']]])
   
}

node('LinuxSlave') {
   echo 'Started execution'
   ansiblePlaybook inventory: '/etc/ansible/ec2.py', extras: '-e \'envType=${stack}\'', playbook: '/home/ec2-user/Release/DryRun.yml'
   echo "Instance created"
   ansiblePlaybook inventory: '/etc/ansible/ec2.py', installation: 'Ansible', playbook: '/home/ec2-user/Release/DryAppRun.yml'   
   print "DEBUG: parameter foo = ${stack}"
}
