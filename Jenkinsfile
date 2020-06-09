@Library('shared-libraries')_

pipeline {
    agent any
    stages {
        stage('Print README') {
            steps {
                script {
                    cleanWs()
                    /* githubscm.checkoutIfExists('github-release-test', */
                        /* "Kevin-Mok", "master", 'kiegroup', */
                        /* "master", false) */
                    /* githubscm.tag('Test', 'test@example.com', 'v1.21') */
                    githubscm.tagRepository('github-release-test',
                        "Kevin-Mok", "master", 'Test',
                        'test@example.com', 'v1.23')
                }
            }
        }
    }
}
