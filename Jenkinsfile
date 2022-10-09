pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/akadakia/spring-petclinicPipelineProject.git', branch: 'main')
        dir(path: 'spring-petclinicPipelineProject')
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