pipeline {
    agent none
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
    
        stage('Test') {
        agent {
        docker { image 'node:16.13.1-alpine' } 
              }
             steps {
                sh 'node --version'
            }
        }
    }
post {
    success {
        mail to: 'Jeya.S@zifornd.com',
             subject: "Success Pipeline: ${currentBuild.fullDisplayName}",
             body: "Something is wrong with ${env.BUILD_URL}"
    }
}

}
