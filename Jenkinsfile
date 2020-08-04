pipeline {
  agent any
  environment {
    GO111MODULES = 'on' 
  }
  tools {
    go 'go-1.14'
  }
  stages {
    stage ('Build') {
      steps {
        sh 'go build'
      }
    }
    stage ('Test') {
      steps {
        sh 'go test ./... -coverprofile=coverage.txt'
      }
    }
    stage('Code Analysis') {
      steps {
        sh 'curl -sfL https://install.goreleaser.com/github.com/golangci/golangci-lint.sh | bash -s -- -b $GOPATH/bin v1.17.1'
        sh 'golangci-lint run'
      }
    } 
  }
}
