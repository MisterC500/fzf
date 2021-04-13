pipeline {
  agent any 
  environment{
      //GOPATH="/working_dir/go/bin"
      PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/go/bin"
      GITHUB_TOKEN = credentials('GH_token')
  }
  stages {
    stage('Compile') {
      steps {
          //sh 'echo "Path is $GOPATH"'
          sh 'go build'
      }   
    }   

    stage('Test') {
      steps { 
          sh 'go test'
      }   
    }   

    stage ('Release') {
      when {
          tag("release-v0.30.0")
      }  

      steps {
          sh 'goreleaser release'
        }   
    }   
  }
}