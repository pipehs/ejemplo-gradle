pipeline {
    agent any
    environment { 
        USER_NAME = 'Felipe Herrera Seguel'
    }
    parameters {choice(name:'CHOICE', choices:['gradle','maven'], description: 'Elección de herramienta de construcción')}
    stages {
        stage('Pipeline') {
            steps {
                script {
                    if (params.CHOICE == 'gradle')
                    {
                        def ejecucion = load 'gradle.groovy'
                        ejecucion.call()
                    }
                    else
                    {
                        def ejecucion = load 'maven.groovy'
                        ejecucion.call()
                    }
                }
            }
        }
    }
    post {
        success {
            slackSend channel: 'U01E2R4SXRN', 
            color: 'good', 
            message: '[${env.USER_NAME}][${env.JOB_NAME}][${params.CHOICE}] Ejecución exitosa', 
            teamDomain: 'dipdevopsusach2020', 
            tokenCredentialId: 'slack-token'
        }
        failure {
            slackSend channel: 'U01E2R4SXRN', 
            color: 'danger', 
            message: '[${env.USER_NAME}][${env.JOB_NAME}][${params.CHOICE}] Ejecución fallida en [${env.STAGE_NAME}]', 
            teamDomain: 'dipdevopsusach2020', 
            tokenCredentialId: 'slack-token'
        }
    }
}