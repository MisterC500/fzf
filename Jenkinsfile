pipeline {
  agent any 
  environment{
      GOPATH="/working_dir/go/bin"
      PATH="${GOPATH}:$PATH"
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
          branch 'master'
        //buildingTag()
      }   

      /*environment {
        GITHUB_TOKEN = credentials('github-token')
      }*/

      steps {
        //sh 'curl -sL https://git.io/goreleaser | bash'
        echo 'Release stage...'
      }   
    }   
  }
}