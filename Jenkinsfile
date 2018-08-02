pipeline {
  agent any
  stages {
    stage ('Initialize') {
      steps {
        git pull origin test-branch
        git push
        echo 'Placeholder.'
      }
    }
  }
}
