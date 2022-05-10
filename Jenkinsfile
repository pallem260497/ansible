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
        } 
      }
      stage ('java installation on nodes') {
        steps {
          sh 'ssh ec2-user@172.31.46.235 -o StrictHostKeyChecking=no'
          sh 'ssh ec2-user@172.31.40.156 -o StrictHostKeyChecking=no'
          sh 'ansible-playbook java.yaml'
        } 
      }
    }
}
