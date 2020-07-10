@Library('jenkins-pipeline-shared-libraries-kmok')_

pipeline {
    agent any
    stages {
        stage('Tag repo') {
            steps {
                script {
                    cleanWs()
                    checkout(githubscm.resolveRepository('jenkins-test', "Kevin-Mok-Bot", "master", false))
                    /* githubscm.tagRepository('Test', 'test@example.com', "$BUILD_TAG", "$BUILD_TAG") */
                    githubscm.tagRepository("$BUILD_TAG", "$BUILD_TAG")
                    /* githubscm.pushObject('origin', "$BUILD_TAG", "bad") */
                }
            }
        }
    }
}
