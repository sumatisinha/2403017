pipeline {
    agent any
  parameters {
    string(name: 'BUILD_NUMBER_INPUT', defaultValue: '1', description: 'Enter build number for deploy step')
  }
    stages {
        stage("build") {
          when {
            branch 'development'
          }
            steps {
                echo 'development branch.....'
            }
        }
        stage("test") {
            steps {
                echo 'testing the application...'
            }
        }
        stage("deploy") {
            steps {
                echo 'deploying the application...   ${params.BUILD_NUMBER_INPUT}'
            }
        }
    }

}
