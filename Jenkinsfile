pipeline {
    agent any

    stages {
        def targetHost = input(
            message: 'Lab IaC:Ingrese la ruta del doc .pem',
            parameters: [string(name: 'SSH_KEY', defaultValue: '')]
        )
        def targetHost = input(
            message: 'Lab IaC:Ingrese el ip de la instancia',
            parameters: [string(name: 'IP_ADDRESS', defaultValue: '')]
        )
        stage('Ejecutar SSH') {
            steps {
                script {
                    sh "ssh -i $SSH_KEY ec2-user@$IP_ADDRESS"
                }
            }
        }

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