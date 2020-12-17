pipeline {
    agent any

    stages {
        stage('Pipelie') {
            steps {
                script {
                    stage('build & test') {
                        sh './gradlew clean build'
                    }
                    stage ('sonar') {
                        def scannerHome = tool 'sonar';
                        withSonarQubeEnv('sonar') {
                            sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=ejemplo-gradle -Dsonar.java.binaries=build"
                        }
                    }
                    stage ('run') {

                    }
                    stage ('rest') {

                    }
                    stage ('nexus') {

                    }
                }
            }
        }
    }
}
