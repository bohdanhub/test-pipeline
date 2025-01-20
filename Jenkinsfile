pipeline {
    agent any

    environment {
        server_name = ""
        server_user_name = ""
        credentials = credentials('aedcf98b-8c4f-4342-9b32-14d3c4b19c2a')
    }

    stages {
        stage('Update and Install Tomcat') {
            steps {
                sshagent([credentials]) {
                    sh """
                    ssh -o StrictHostKeyChecking=no $server_user_name@$server_name << EOF
                      sudo apt update
                      sudo apt install -y tomcat9
                    EOF
                    """
                }
            }
        }
    }
}