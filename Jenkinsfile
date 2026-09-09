pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Test') {
      steps {
        sh 'python3 -m unittest discover -s tests -p "test_*.py" -v'
      }
    }

    stage('Build Check') {
      steps {
        sh 'test -f index.html && test -f css/style.css && test -f js/script.js'
      }
    }
  }

  post {
    success {
      echo 'Warranty Vault CI passed.'
    }

    failure {
      echo 'Warranty Vault CI failed.'
    }
  }
}
