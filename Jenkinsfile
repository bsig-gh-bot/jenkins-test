pipeline {
    agent any
    stages {
        stage('Input') {
            input {
                message "Enter staging repository URL: "
                parameters {
                    string(name: 'STAGING_REPO_URL', description: 'Staging repository URL.')
                }
            }
            steps {
                echo "${STAGING_REPO_URL}"
                writeFile(file: "staging-url.txt", text: "${STAGING_REPO_URL}")
            }
        }
        stage('Archive URL') {
            steps {
                archiveArtifacts(artifacts: "staging-url.txt")
            }
        }
    }
}
