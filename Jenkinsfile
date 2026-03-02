pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                echo 'Забираем код из GitHub...'
                checkout scm
            }
        }

        stage('Check Files') {
            steps {
                echo 'Проверяем созданные файлы...'
                sh '''
                    ls -la

                    if [ -f Dockerfile ]; then
                        echo "Dockerfile найден"
                    else
                        echo "Dockerfile не найден"
                    fi

                    if [ -f requirements.txt ]; then
                        echo "requirements.txt найден"
                    else
                        echo "requirements.txt не найден"
                    fi

                    if [ -f src/app.py ]; then
                        echo "src/app.py найден"
                    else
                        echo "src/app.py не найден"
                    fi
                '''
            }
        }

        stage('Docker Theory') {
            steps {
                echo 'Docker команды теоретически выполняются'
            }
        }
    }

    post {
        success {
            echo 'ОТЛИЧНО! CI/CD работает!'
        }
        failure {
            echo 'Есть ошибки!'
        }
    }
}
