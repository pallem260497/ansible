pipeline {
  agent any
  tools {
      jdk 'jdk11'
      git 'Default'
      maven 'maven'
  }
    stages {
      stage ('gitclone') {
        steps {
          git branch: 'master', url: 'https://github.com/pallem260497/ansible.git'
        } 
      }
      stage ('listGit') {
        steps {
          sh 'ls -lr'
        } 
      }
      stage ('maven') {
        steps {
          sh 'mvn clean package'
        } 
      }
      stage ('listmaven') {
        steps {
          sh 'ls -lr'
        } 
      }
      stage ('maven path') {
        steps {
          sh 'pwd'
          sh 'whoami'
        } 
      }
      stage ('ansible version') {
        steps {
          sh 'ansible --version'
        } 
      }
      stage ('ansible pwd') {
        steps {
          sh 'pwd' 
          sh 'whoami'
          
        } 
      }
      stage ('java installation on nodes') {
        steps {
          ansiblePlaybook credentialsId: 'private-key1', disableHostKeyChecking: true, installation: 'ansible',  playbook: 'tomcat.yaml' {
          sh "ansible-playbook tomcat.yaml"
          }
        } 
      }
    }
}
