pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "building"
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                exit 1
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
