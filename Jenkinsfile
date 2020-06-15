@Library('shared-libraries')_

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
                    githubscm.checkoutIfExists('github-release-test',
                        "Kevin-Mok", "master", 'kiegroup',
                        "master", false)
                    githubscm.tagRepository('Test', 'test@example.com', "$BUILD_TAG", "$BUILD_TAG")
                    githubscm.pushObject('origin', "$BUILD_TAG", "bad")
                }
            }
        }
    }
}
