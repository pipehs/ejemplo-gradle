pipeline {
    agent any
    parameters = {choice(name:'CHOICE', choices:['gradle','maven'], description: 'Elección de herramienta de construcción')}
    stages {
        stage('Pipeline') {
            steps {
                script {
                    echo 'Herramienta de ejecución seleccionada: ' ${params.CHOICE}
                    def ejecucion = (params.CHOICE == 'gradle') ? load 'gradle.groovy' : load 'maven.groovy'
                    ejecucion.call()
                }
            }
        }
    }
}
