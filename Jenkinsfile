pipeline {
    agent any

    environment {
        APP = 'Aplicación de prueba'
        ENTORNO='QUA'
        MENSAJE='esto solo es una prueba'
    }

    stages {
        stage('Info') {
            steps {
                echo "APP=${env.APP}"
                echo "ENTORNO=${env.ENTORNO}"
                echo "MENSAJE=${env.MENSAJE}"
                echo "Mi proyecto es:= ${env.JOB_NAME}"
                echo "El número de build es:=${BUILD_NUMBER}"
            
            }
        }

        stage('Aprobacion') {
            steps {
                input message: "¿Continuar?", ok: 'Continuar'
            }
        }

        stage('Simular despliegue') {
            steps {
                echo "Desplegando..."
            }
        }
    }

    post {
        success {
            echo "OK: build exitoso."
        }
        failure {
            echo "ERROR: build fallido."
        }
        aborted {
            echo "CANCELADO: se abortó en el input o manualmente."
        }
        always {
            echo "FIN: este bloque siempre se ejecuta."
        }
    }
}
