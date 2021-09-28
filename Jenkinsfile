 pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                 sh 'npm i -D jest-sonar-reporter'
                 sh 'npm install --save-dev jest'
                 sh 'npm start'
                 sh 'rm -f test-report.xml'
                 sh 'touch test-report.xml'             }
        }
        stage('Test'){
             steps{
                sh 'npm test --coverage'
                
              }
        }
      
          post {
       always {
              junit 'sonar-scanner   -Dsonar.projectKey=JavaScript   -Dsonar.sources=.   -Dsonar.host.url=http://localhost:9000   -Dsonar.login=991c09e71a1757105dd603e412947afc17331b36
           }
  }
}
