@Library('jenkins-pipeline-shared-libraries')_

pipeline {
    agent any
    parameters {
        booleanParam(name: 'RELEASE', defaultValue: true, description: 'Is this build for a release?')
    }
    stages {
        stage('Clone repositories') { 
            when {
                expression { return params.RELEASE }
            }
            steps {
                echo "RELEASE"
            }
        }
    }
}
