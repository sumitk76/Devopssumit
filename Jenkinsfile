pipeline {
    agent any
    stages {
        stage('Connect to SSH Server') {
            steps {
                    def remote = [:]
                    remote.name = 'myRemoteHost' // A descriptive name for the remote host
                    remote.host = '172.21.219.211'
                    remote.user = 'sumit'
                    remote.allowAnyHosts = true // Set to false in production and manage known_hosts
                    remote.password = 'Rchik@6824'
                    sshscript remote: remote, script: readFile('remote_script.sh'), failOnError: true
            }
        }
    }
}
