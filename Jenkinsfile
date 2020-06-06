@Library('shared-libraries')_

pipeline {
    agent any
    stages {
        stage('Print README') {
            steps {
                dir("github-release-test") {
                    script {
                        githubscm.checkoutIfExists('github-release-test',
                        "$CHANGE_AUTHOR", "test", 'kiegroup', "$CHANGE_TARGET", true)
                        /* println sh(returnStdout: true, script: 'cat README.md').trim() */
                        /* sh(returnStdout: true, script: 'cat README.md').trim() */
                        /* sh "git status" */
                        sh "ls -la"
                    }
                }
            }
        }
    }
}
