pipeline {
  agent any
  tools {nodejs "node"}
  stages {
      
    stage('build' ) {
      steps {
         sh 'npm install'
         echo "Build Number: ${env.BUILD_NUMBER}"
        } 
      }

    stage('Test' ) {
      // Test cases only execute when branch name should dev
      when {
        expression {
          // BRANCH_NAME is env variable in jenkins
          env.BRANCH_NAME == 'dev'
        }
      }

      steps {
         echo 'Testing the application'
        } 
      }

      stage('Config'){
        steps {
          sh 'serverless config credentials --provider aws --key AKIAUW4BFBH3LUN6IG66 --secret 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 --profile serverlessUser'
          echo 'Serverless profile create successfully'
        }
      }

      stage('Deploy' ) {
        steps {
           sh 'sls deploy'
          } 
        }
    }

// Post statement used for notify the pipe line 
    // post {
    //   always {
    //    // execute every time when pipe line
    //    echo 'always execute'
    //   }
    //   failure {
    //    // excute this statment when pipe line failed
    //    echo 'failure case execute'
    //   }
    //   success {
    //     // execute this statement when pipe line was successed
    //     echo 'success execute'
    //   }
    // }
}