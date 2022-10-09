pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/akadakia/spring-petclinicPipelineProject.git', branch: 'main')
      }
    }

    stage('Result') {
      steps {
        echo 'Successful clone'
      }
    }

  }
}