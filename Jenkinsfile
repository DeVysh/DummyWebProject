node('master') {
  checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/DeVysh/DummyWebProject.git']]])
  
  powershell '''$filepath = \'"C:\\Program Files (x86)\\Jenkins\\workspace\\JenkinsPipeline\\indexWeb.html"\'
Start-Process \'C:\\Program Files\\PuTTY\\pscp.exe\' -ArgumentList ("-scp -pw open@123 $filepath vyshakh@13.210.78.89:/home/ec-user/Release/") '''

powershell '''$filepath = \'"C:\\Program Files (x86)\\Jenkins\\workspace\\JenkinsPipeline\\indexApp.html"\'
Start-Process \'C:\\Program Files\\PuTTY\\pscp.exe\' -ArgumentList ("-scp -pw open@123 $filepath vyshakh@13.210.78.89:/home/ec-user/Release/") '''

powershell '''$filepath = \'"C:\\Program Files (x86)\\Jenkins\\workspace\\JenkinsPipeline\\CloudFormation_Vysh.cform"\'
Start-Process \'C:\\Program Files\\PuTTY\\pscp.exe\' -ArgumentList ("-scp -pw open@123 $filepath vyshakh@13.210.78.89:/var/destfolder/") '''
}

node('LinuxSlave') {
   echo 'Started execution'
   ansiblePlaybook inventory: '/etc/ansible/ec2.py', extras: '-e \'envType=${stack}\'', playbook: '/home/ec2-user/Release/DryRun.yml'
   echo "Instance created"
   ansiblePlaybook inventory: '/etc/ansible/ec2.py', installation: 'Ansible', playbook: '/home/ec2-user/Release/DryAppRun.yml'   
   print "DEBUG: parameter foo = ${stack}"
}
