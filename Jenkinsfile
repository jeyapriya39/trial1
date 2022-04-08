pipeline {
    stages {
           stage('Build') {
            agent any
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
        stage('Test') {
        agent {
        docker { image 'node:16.13.1-alpine' } 
             steps {
                sh 'node --version'
            }
        }
    }

}
