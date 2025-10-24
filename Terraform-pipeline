pipeline {
    agent any

    environment {
        USER = "sumit"
        HOST = "172.21.219.211"
        PASSWORD = "Rchik@6824"
        PORT = "22"
    }

    stages {
        stage('Connect to SSH Server') {
            steps {
                sh '''
                    #!/bin/bash
                    sshpass -p "$PASSWORD" ssh -o StrictHostKeyChecking=no -p $PORT $USER@$HOST << EOF
                    echo "Connected to $HOST"
                    hostname
                    uptime
                    EOF
                '''
            }
        }
    }
}
