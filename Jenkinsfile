pipeline {
    agent any

    stages {
        stage('Instalar paquete en EC2') {
            steps {
                script {
                    def targetHost = input(
                        message: 'Lab IaC: 44.215.121.231',
                        parameters: [string(name: 'targetHost', defaultValue: 'ec2-44-215-121-231.compute-1.amazonaws.com')]
                    )
                    sh "/usr/local/bin/ansible-playbook -i '${targetHost},' playbooks/install_app.yml -e 'target_host=${targetHost}'"
                }
            }
        }
    }

}