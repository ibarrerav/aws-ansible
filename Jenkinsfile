pipeline {
    agent any

    stages {
        stage('Instalar paquete en EC2') {
            steps {
                script {
                    def targetHost = input(
                        message: 'Lab IaC: 172.31.3.212',
                        parameters: [string(name: 'targetHost', defaultValue: '172.31.3.212')]
                    )
                    sh "/usr/local/bin/ansible-playbook -i '${targetHost},' playbooks/install_app.yml -e 'target_host=${targetHost}'"
                }
            }
        }
    }

}