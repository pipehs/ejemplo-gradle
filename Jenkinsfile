pipeline {
    agent any

    stages {
        stage('Pipeline') {
            steps {
                script {
                    stage('build & test') {
                        sh './gradlew clean build'
                    }
                    stage ('sonar') {
                        def scannerHome = tool 'sonar';
                        withSonarQubeEnv('Sonar') {
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
