pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        tool 'openjdk-19'
        git(url: 'https://github.com/akadakia/spring-petclinicPipelineProject.git', branch: 'main')
        dir(path: '/home/ubuntu/spring-petclinicPipelineProject') {
          echo 'Directory change complete'
        }

        sh './mvnw package'
        echo 'Build complete.'
      }
    }

    stage('Test') {
      steps {
        echo 'Tests in PetClinic Build Completed Successfully'
        isUnix()
        echo 'Test Successful'
        fileExists 'Dockerfile.cp'
        echo 'Test Successful'
      }
    }

    stage('Package') {
      steps {
        tool 'MAVEN_TOOL'
        dir(path: '/home/ubuntu/spring-petclinicPipelineProject') {
          echo 'adding body to dir step'
        }

        sh 'mvn install -DskipTests'
        sh 'docker build -f ./Dockerfile.cp -t spring/petclinic .'
        sh 'docker save --output springPC.tar spring/petclinic'
        echo 'Completed packaging.'
      }
    }

    stage('Result') {
      steps {
        echo 'Pipeline completed successfully.'
      }
    }

  }
}