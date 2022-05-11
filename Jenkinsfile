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
          sh 'sudo su ec2-user'
          sh 'whoami'
        } 
      }
      stage ('java installation on nodes') {
        steps {
          ansiblePlaybook credentialsId: 'private-key', disableHostKeyChecking: true. installation: 'ansible', inventory: 'dev.inv', playbook: 'tom.yaml'
          
        } 
      }
    }
}
