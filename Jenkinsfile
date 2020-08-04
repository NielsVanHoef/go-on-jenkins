pipeline {
  agent any
  environment {
    GO111MODULES = 'on' 
  }
  tools {
    go 'go-1.14'
  }
  stages {
    stage {
      steps {
        sh 'go build'
      }
    }
  }
}
