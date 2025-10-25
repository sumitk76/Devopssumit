pipeline {
    agent any
    stages {
        stage('Remote SSH Execution') {
            steps {
                script {
                    // Define remote server details
                    def remote = [:]
                    remote.name = 'myRemoteServer'
                    remote.host = '172.21.219.211' // Replace with your host
                    remote.user = 'sumit' // Replace with your username
                    remote.password = 'Rchik@6824' // Replace with your password or use SSH keys for better security
                    remote.allowAnyHosts = true // Set to false in production and manage known hosts

                    // Create a shell script file on the Jenkins agent
                    writeFile file: 'remote_script.sh', text: '''
                    #!/bin/bash
                        echo "Hello from the remote server!"
                        hostname
					echo "=============================================="
					echo "going to terraform directorty";
                    cd /home/sumit/learn-terraform-get-started-aws   
                    echo "<<<<<....Wait for terrform to start....>>>>>>>>>"
                    sleep 5
					terraform init
					terraform plan
					sleep 5
					terraform apply
					sleep 30
					echo "Find below terrform result";
                    echo "END";
                    '''

                    // Execute the script on the remote server
                    sshScript remote: remote, script: 'remote_script.sh'
                }
            }
        }
       }
    }
