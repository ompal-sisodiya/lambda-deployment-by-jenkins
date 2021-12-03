pipeline {
  agent any
  tools {nodejs "node"}
  stages {
      
    stage('build' ) {
      steps {
         //sh 'npm install'
         echo 'building the application'
        } 
      }

    stage('Test' ) {
      steps {
         echo 'Testing the application'
        } 
      }

      stage('Deploy' ) {
        steps {
          echo 'Deploy the application'
          } 
        }
    }
}