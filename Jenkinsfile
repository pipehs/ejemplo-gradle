pipeline {
    agent any
    parameters {choice(name:'CHOICE', choices:['gradle','maven'], description: 'Elección de herramienta de construcción')}
    stages {
        stage('Pipeline') {
            steps {
                script {
                    if (params.CHOICE == 'gradle')
                    {
                        def ejecucion = load 'gradle.groovy'
                    }
                    else
                    {
                        def ejecucion = load 'maven.groovy'
                    }
                }
            }
        }
    }
}
