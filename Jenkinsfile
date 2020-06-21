pipeline {
    agent any
    /* parameters {
        booleanParam(name: 'RELEASE', defaultValue: false, description: 'Is this build for a release?')
    } */
    stages {
        stage('Archive staging repository URL') {
            steps {
                script {
                    /* if (params.RELEASE) { */
                    /* } */
                    def PROPERTIES_FILE = "deployment.properties"
                    sh "wget --auth-no-challenge --user=kevin --password=112ef7228e7a8cea5435473f9416cb56e1 http://localhost:8090/job/2286/lastSuccessfulBuild/artifact/deployment.properties -O ${PROPERTIES_FILE}"
                    def props = readProperties file:"${PROPERTIES_FILE}"
                    def Var1= props['STAGING_REPO_URL']
                    echo "Var1=${Var1}"
                }
            }
        }
    }
}
