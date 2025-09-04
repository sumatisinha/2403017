// A Jenkinsfile that defines a declarative pipeline with a parameter and conditional stages.
pipeline {
    agent any

    // The 'parameters' block defines inputs that a user can provide
    // when running the pipeline.
    parameters {
        string(name: 'BUILD_NUMBER_INPUT', defaultValue: '1', description: 'Enter build number for deploy step')
    }

    // The 'stages' block contains the sequential stages of the pipeline.
    stages {
        // ---
        // Stage 1: Build
        // This stage will only run if the current Git branch is "development".
        stage("Build") {
            when {
                branch 'development'
            }
            steps {
                echo 'Building on the development branch...'
                // Add your build commands here
            }
        }

        // ---
        // Stage 2: Test
        // This stage runs on all branches.
        stage("Test") {
            steps {
                echo 'Running tests on the application...'
                // Add your test commands here
            }
        }

        // ---
        // Stage 3: Deploy
        // This stage runs on all branches and uses the user-provided parameter.
        stage("Deploy") {
            steps {
                echo "Deploying the application with build number: ${params.BUILD_NUMBER_INPUT}"
                // Add your deploy commands here using the 'BUILD_NUMBER_INPUT'
            }
        }
    }
}
