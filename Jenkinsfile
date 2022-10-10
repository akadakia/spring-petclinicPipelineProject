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
        echo 'Build complete.'
      }
    }

    stage('Test') {
      steps {
        echo 'Test Test 123'
      }
    }

    stage('Package') {
      steps {
        dir(path: '/home/ubuntu/spring-petclinicPipelineProject') {
          echo 'adding body to dir step'
        }

        sh 'mvn install -DskipTests'
        sh 'docker build -f ./Dockerfile.cp -t spring/petclinic .'
        echo 'Completed packaging.'
        tool 'mav'
      }
    }

    stage('Result') {
      steps {
        echo 'Pipeline completed successfully.'
      }
    }

  }
}