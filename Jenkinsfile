
timestamps {
    node("windows"){
        prepareEnv()
    }
    
    parallel WinBuild: {
        stage('Test on windows') {
            echo "test"
            echo env.BRANCH_NAME
            echo "yes this"
        }
    }, MacBuild: {
        stage('Test on Mac'){
            echo "test"
        }
    },
    failFast: true
}


def prepareEnv() {
    echo env.BRANCH_NAME
    echo env.GIT_URL
    env.media_sdk3_branch = ""
    env.media_sdk3_private_branch = ""
}
