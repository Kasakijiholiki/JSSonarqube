pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
             sh 'npm test -- --coverage'
             }
        }
    }
    post {
        always {
         sh'sonar-scanner   -Dsonar.projectKey=JavaScript   -Dsonar.sources=.   -Dsonar.host.url=http://localhost:9000   -Dsonar.login=991c09e71a1757105dd603e412947afc17331b36'
         }
    
    }
}
