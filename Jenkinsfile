pipeline {
  agent any
  stages {
    stage ('Initialize') {
      steps {
        echo 'Welcome to the Pipeline.'
        bat 'git pull origin test-branch'
        bat 'git push'
      }
    }
  }
}
