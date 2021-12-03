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
      // Test cases only execute when branch name should dev
      when {
        expression {
          // BRANCH_NAME is env variable in jenkins
          BRANCH_NAME == 'dev'
        }
      }

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

// Post statement used for notify the pipe line 
    post {
      always {
       // execute every time when pipe line
      }
      failure {
       // excute this statment when pipe line failed
      }
      success {
        // execute this statement when pipe line was successed
      }
    }
}