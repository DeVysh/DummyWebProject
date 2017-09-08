node('master') {
  checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/DeVysh/DummyWebProject.git']]])
   PowerShell("C:\FileTransfer\copyfileWeb.ps1") 
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

def PowerShell(psCmd) {
    bat "powershell.exe -NonInteractive -ExecutionPolicy Bypass -Command \"\$ErrorActionPreference='Stop';[Console]::OutputEncoding=[System.Text.Encoding]::UTF8;$psCmd;EXIT \$global:LastExitCode\""
}