
timestamps {
    node("Mac"){
        prepareEnv()
    }
    
    parallel WinBuild: {
        stage('Test on windows') {
            echo "test"
            echo env.BRANCH_NAME
        }
    }, MacBuild: {
        stage('Test on Mac'){
            echo "test"
        }
    },
    failFast: true|false
}


def prepareEnv() {
    echo env.BRANCH_NAME
    echo env.GIT_URL
    echo sh(script: 'env|sort', returnStdout: true)
    env.media_sdk3_branch = ""
    env.media_sdk3_private_branch = ""
    result = sh (script: "git log -1 | grep 'need investigate'", returnStatus: true) 
    echo result
}