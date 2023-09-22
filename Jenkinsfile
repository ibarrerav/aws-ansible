pipeline {
    agent any

    stages {
        stage('Instalar paquete en EC2') {
            steps {
                script {
                    def targetHost = input(
                        message: 'Lab IaC:Ingrese su instancia',
                        parameters: [string(name: 'targetHost', defaultValue: '')]
                    )
                    sh "/usr/local/bin/ansible-playbook -i '${targetHost},' playbooks/install_app.yml -e 'target_host=${targetHost} ansible_user=ec2-user'"
                }
            }
        }
    }
}