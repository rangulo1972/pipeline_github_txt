pipeline {
    agent any

    triggers {
        githubPush() // Escucha eventos de push en el repositorio
    }

    stages {
        stage('Simular error en el job') {
            steps {
                script {
                    exit 1
                }
            }
        }
    }

    post {
        failure {
            echo 'Error en el pipeline. Enviando notificación por correo...'
            mail to: 'rangulo1972@gmail.com',
                subject: "Error en el Pipeline en la rama Lunes",
                body: "Error ejecutado en la rama Lunes del repositorio."
        }
    }
}