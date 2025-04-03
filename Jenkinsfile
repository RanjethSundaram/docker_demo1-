pipeline {
  agent any
  stages {
    stage('buildStage') {
      steps {
        git(url: 'https://github.com/RanjethSundaram/docker_demo1-', branch: 'master', credentialsId: 'github')
        sh 'docker build -t ranjethsundaram/devops_demo1:img1 .'
      }
    }

    stage('DEV&QA') {
      parallel {
        stage('devDeploy') {
          steps {
            sh 'docker push ranjethsundaram/devops_demo1:img1'
          }
        }

        stage('deployQA') {
          steps {
            echo 'QA stage is comepleted'
          }
        }

      }
    }

  }
}