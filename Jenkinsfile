pipeline {
    agent any

    triggers {
        githubPush() // Escucha eventos de push en el repositorio
    }

    environment {
        RECIPIENT_EMAIL = 'rangulo1972@gmail.com' // Correo para notificaciones
    }

    stages {
        stage('Simular error en el job') {
            steps {
                script {
                    echo 'Simulación del error en el job'
                    sh asdasd // comando a realizar el error de ejecución del job
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
            mail to: "${RECIPIENT_EMAIL}",
                subject: "Error en el Pipeline: pipeline-git-simple-rama-Lunes",
                body: "Error ejecutado en la rama Lunes del repositorio."
        }
    }
}