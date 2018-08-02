pipeline {
  agent any
  
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
      
      input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PROD_DEPLOY', defaultValue: 'No', description: 'Perform Prod Deployment?')
                }
            }
      
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
