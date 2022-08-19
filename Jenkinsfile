pipeline{
    agent any
    stages{
        stage('clone code'){
            steps{
                git credentialsId: 'githubcredentials', url: 'https://github.com/demuduraviteja/hello-world.git'
            }
        }
        stage('build code'){
            steps{
                sh 'mvn clean install'
            }
        }
        stage('Execute ansible playbook'){
            steps{
             ansiblePlaybook credentialsId: 'tomcat-private-key', disableHostKeyChecking: true, installation: 'ansible', inventory: 'hosts.yml', playbook: 'ansible.yml'   
            }
        }
    }
}
