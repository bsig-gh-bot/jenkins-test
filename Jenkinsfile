pipeline {
    agent any
    environment {
        PROPERTIES_FILE_NAME = "deployment.properties"
    }
    parameters {
        booleanParam(name: 'RELEASE', defaultValue: true, description: 'Is this build for a release?')
        string(name: 'DEPLOY_PROPERTIES_URL', defaultValue: 'http://localhost:8090/job/2415/28/artifact/deployment.properties', description: 'Only needed if RELEASE. URL to archived deployment.properties file from deploy pipeline.')
    }
    stages {
        stage('Approve promotion') {
            when {
                expression { return params.RELEASE && params.DEPLOY_PROPERTIES_URL != '' }
            }
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'kmok-jenkins', usernameVariable: 'JENKINS_USER', passwordVariable: 'JENKINS_TOKEN')]) {
                        sh "wget --auth-no-challenge --user=${JENKINS_USER} --password=${JENKINS_TOKEN} ${DEPLOY_PROPERTIES_URL} -O ${PROPERTIES_FILE_NAME}"
                    }
                    sh "cat ${PROPERTIES_FILE_NAME}"
                }
            }
        }
    }
}
