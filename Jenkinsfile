pipeline {
    agent any
    stages {
        stage('version checks'){
            sh 'mvn -v'
        }
        stage('Build') {
            steps {
                echo 'cleaning'
                sh './mvnw clean' 
            }
        }
        stage('Test') {
            steps {
                echo 'testing'
                sh './mvnw test' 
            }
        }
        stage('Package') {
            steps {
                echo 'packaging'
                sh './mvnw package' 
            }
        }
        stage('Deploy') {
            when {
                branch 'master'
            }
            steps {

                sh './mvnw deploy' 
            }
        }

    }    
  }
    post {
        success {
            emailext(attachLog: false,
                        body: 'pipeline failed', 
                        subject: 'sage4se pipeline failure', 
                        to: 'oshatout@hotmail.com')
        }
        failure {
            emailext(attachLog: true,
                        body: 'pipeline failed', 
                        subject: 'sage4se pipeline failure', 
                        to: 'oshatout@hotmail.com')
        }
        
    }
}