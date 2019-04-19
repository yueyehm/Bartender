
pipeline {
    agent any
    options { timestamps () }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            echo env.BRANCH_NAME
            echo sh(script: 'env|sort', returnStdout: true)
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}



