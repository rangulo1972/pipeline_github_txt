pipeline {
    agent any

    triggers {
        githubPush() // Escucha eventos de push en el repositorio
    }

    stages {
        stage('Simular error en el job') {
            steps {
                script {
                    echo 'Simulación del error en el job...'
                    sh '''
                    echo "Iniciando prueba simple..."
                    exit 1 # Simula un error
                    '''asdasd
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline ejecutado correctamente.'
        }
        failure {
            echo 'Error en el pipeline. Enviando notificación por correo...'
            mail to: 'rangulo1972@gmail.com',
                subject: "Error en el Pipeline: pipeline-git-simple-rama-Lunes",
                body: "Error ejecutado en la rama Lunes del repositorio."
        }
    }
}