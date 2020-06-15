pipeline {
    agent any
    parameters {
        booleanParam(name: 'RELEASE', defaultValue: false,
            description: 'Is this build for a release?')
    }
    stages {
        stage('Tag repo') {
            steps {
                script {
                    cleanWs()
                    if(params.RELEASE) {
                        echo "Yes equal - running the stage"
                    } else {
                        echo "Not equal - skipping the stage"
                    }
                }
            }
        }
    }
}
