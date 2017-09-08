node('master') {
  checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/DeVysh/DummyWebProject.git']]])
   powershell '''$filepath = \'"C:\\Program Files (x86)\\Jenkins\\workspace\\JenkinsPipeline\\indexWeb.html"\'
Start-Process \'C:\\Program Files\\PuTTY\\pscp.exe\' -ArgumentList ("-scp -pw open@123 $filepath vyshakh@13.210.78.89:/var/destfolder/") '''
   print "DEBUG: parameter foo = ${stack}"
}

node('LinuxSlave') {
   echo 'Started execution'
   /*ansiblePlaybook forks: 5, installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/home/ec2-user/Release/cloudStack_SingleInstance.yml'
   echo 'Instance is created.'
   ansiblePlaybook forks: 5, installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/var/jenkins/workspace/JenkinsPipeline/windows_hellowworld.yml'
   echo 'Ansible is triggered'*/
   print "DEBUG: parameter foo = ${stack}"
}
