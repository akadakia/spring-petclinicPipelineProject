pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        tool 'openjdk-19'
        git(url: 'https://github.com/akadakia/spring-petclinicPipelineProject.git', branch: 'main')
        dir(path: '/home/ubuntu/spring-petclinicPipelineProject') {
          echo 'Adding body in support of "dir" command'
        }

        sh './mvnw package'
        sh 'java -jar target/*.jar'
      }
    }

    stage('Test') {
      steps {
        echo 'Test Test 123'
      }
    }

    stage('Package') {
      steps {
        sh './mvnw spring-boot:build-image'
      }
    }

    stage('Result') {
      steps {
        echo 'Pipeline completed successfully.'
      }
    }

  }
}