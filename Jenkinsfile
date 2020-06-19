pipeline {
    agent any
    stages {
        stage('Archive staging repository URL') {
            steps {
                script {
                    def STAGING_REPO_URL = input(message: "Enter staging repository URL:", parameters: [text(name: 'STAGING_REPO_URL')])
                    def STAGING_URL_FILE = "staging-url.txt"
                    def PROPERTIES_FILE = "deployment.properties"
                    sh "echo ${STAGING_REPO_URL} > ${STAGING_URL_FILE}"
                    sh "printf \"STAGING_REPO_URL=%s\" \"${STAGING_REPO_URL}\" > ${PROPERTIES_FILE}"
                    writeFile(file: "${STAGING_URL_FILE}", text: "${STAGING_REPO_URL}")
                    archiveArtifacts(artifacts: "${STAGING_URL_FILE}, ${PROPERTIES_FILE}")
                }
            }
        }
    }
}
