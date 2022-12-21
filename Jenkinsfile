pipeline {
  agent any
  stages {
    stage('log tool versions') {
      parallel {
        stage('log tool versions') {
          steps {
            sh '''mvn --version
git --version
java --version'''
          }
        }

        stage('Check for pom') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('build with maven') {
      steps {
        sh 'mvn compile test package'
      }
    }

    stage('post build step') {
      steps {
        writeFile(file: 'status.txt', text: 'hey it worked!!')
      }
    }

  }
}