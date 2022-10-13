pipeline {
  agent any
  stages {
    stage('Worked on Node ') {
      parallel {
        stage('Worked on Node ') {
          steps {
            node(label: 'worker1') {
              sh '''git --version
mvn --version 
java --version'''
            }

          }
        }

        stage('check pom file') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('Build with Maven') {
      steps {
        sh 'mvn compile test package'
      }
    }

    stage('Post build Action') {
      steps {
        writeFile(file: 'status', text: 'Hey its Worked!!')
      }
    }

  }
  environment {
    worker1 = 'worker1'
  }
}