pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                branches: [[name: '*/main']],
                userRemoteConfigs: [[url: 'https://github.com/harinivenky/PES2UG21CS186_Jenkins.git']]])
            }
        }
        stage('Build'){
            steps {
                build 'PES2UG21CS186-1'
                sh 'g++ hi.cpp -o output'
            }
        }
        stage('Test')
        {
            steps {
                sh './output'
            }
        }
        stage('Deploy')
        {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure{
            error 'Pipeline failed'
        }
    }
}
