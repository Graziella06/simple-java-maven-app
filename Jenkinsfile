pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2  --network=host'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('NewStep') {
      parallel {
        stage('NewStep') {
          steps {
            sh 'echo " new Step" '
          }
        }
        stage('parallelTask') {
          steps {
            echo '" PARALLEL TASK"'
          }
        }
      }
    }
  }
}