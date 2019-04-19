pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            echo env.BRANCH_NAME
            echo env
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

