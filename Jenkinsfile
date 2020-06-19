@Library('jenkins-pipeline-shared-libraries')_

pipeline {
    agent any
    parameters {
        booleanParam(name: 'RELEASE', defaultValue: true, description: 'Is this build for a release?')
        /* booleanParam(name: 'RELEASE', defaultValue: false, description: 'Is this build for a release?') */
    }
    stages {
        stage('Archive staging repository URL') {
            steps {
                script {
                    if (params.RELEASE) {
                        /* input message "Enter staging repository URL:" parameters { string(name: 'STAGING_REPO_URL') } */
                        /* input(message: "Enter staging repository URL:", parameters: [[$class: 'TextParameterDefinition', name: 'STAGING_REPO_URL']]) */
                        writeFile(file: "staging-url.txt", text: input(message: "Enter staging repository URL:", parameters: [text(name: 'STAGING_REPO_URL')]))
                        archiveArtifacts(artifacts: "staging-url.txt")
                    } else {
                        echo "not RELEASE"
                    }
                }
            }
        }
    }
}
