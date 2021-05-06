pipeline {
    agent any 
    stages {
        stage('Update Configuration') {
            steps {
                // Store the configuration in Jenkins
                archiveArtifacts(
                    artifacts: 'environment',
                    fingerprint: false
                )
            }
        }
    }
}
