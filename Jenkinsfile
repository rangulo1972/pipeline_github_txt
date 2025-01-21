pipeline {
    agent any

    triggers {
        githubPush() // Escucha eventos de push en el repositorio
    }

    stages {
        stage('Correcto') {
            steps {
                script {
                    sh "cat archivo1.txt"
                }
            }
        }
        stage('Incorrecto') {
            steps {
                script {
                    cho "mensaje de error"
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
