pipeline {
    agent any
    environment {
        GITHUB_TOKEN = credentials('nzxt-jenkins')
        GOPATH = "$WORKSPACE/go"
        PATH = "$PATH:$GOPATH/bin"
    }
    stages {
        stage('Release') {
            steps {
                script {
                    sh """
                    echo $PATH
                    go get github.com/github-release/github-release
                    github-release info -u Kevin-Mok -r github-release-test
                    """
                }
            }
        }
    }
}
