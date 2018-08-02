pipeline {
  agent any
  stages {
    stage ('Initialize') {
      steps {
        echo 'Welcome to the Pipeline.'
        bat '"C:\Program Files\Git\bin\git" pull origin test-branch'
        bat '"C:\Program Files\Git\bin\git" push'
      }
    }
  }
}
