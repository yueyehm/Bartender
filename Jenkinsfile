
pipeline {
    agent any
    options { timestamps () }
    stages {
        stage('Build') {
            node("Mac"){
                    steps {
                    echo 'Building..'
                    echo env.BRANCH_NAME
                    echo sh(script: 'env|sort', returnStdout: true)
                    prepareEnv()
                }
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


def prepareEnv() {
    echo env.BRANCH_NAME
    echo env.GIT_URL
    echo sh(script: 'env|sort', returnStdout: true)
    env.media_sdk3_branch = ""
    env.media_sdk3_private_branch = ""
    checkout changelog: false, scm: [
        $class: 'GitSCM',
        branches: [ [ name: env.BRANCH_NAME ] ],
        browser: [ $class: 'GitWeb', repoUrl: env.GIT_URL ],
        extensions: [
        [ $class: 'LocalBranch', localBranch: env.BRANCH_NAME ],
        [ $class: 'CloneOption', noTags: false, reference: '', shallow: true ]
        ],
        userRemoteConfigs: [ [ credentialsId: 'dbbbd469-576f-495a-a384-ec673d3417ee', url: env.GIT_URL ] ]
    ]
    result = sh (script: "git log -1 | grep 'need investigate'", returnStatus: true) 
    echo result
}


