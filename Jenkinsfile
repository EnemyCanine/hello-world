pipeline {
  agent any
  parameters {
        choice(
            // choices are a string of newline separated values
            // https://issues.jenkins-ci.org/browse/JENKINS-41180
            choices: 'Yes\No',
            description: 'Prod Deployment',
            name: 'PROD_DEPLOY')
    }
  stages {
    stage ('Initialize') {
      steps {
        echo 'Welcome to the Pipeline.'
        //bat '"C:\\Program Files\\Git\\bin\\git" pull origin test-branch'
        //bat '"C:\\Program Files\\Git\\bin\\git" push'
      }
    }
    stage ('Verify') {
      steps {
        echo 'Verifying valid build.' 
      }
    }
    stage ('Branch') {
            when {
                // Only say hello if a "greeting" is requested
                expression { params.PROD_DEPLOY == 'Yes' }
            }
            steps {
                echo "Performing Prod Deployment!"
            }
            when {
                // Only say hello if a "greeting" is requested
                expression { params.PROD_DEPLOY == 'No' }
            }
            steps {
                echo "Starting Dev Deployment"
            }
        }
  }
}
