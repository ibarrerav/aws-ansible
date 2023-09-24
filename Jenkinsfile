pipeline {
    agent any

    stages {
        /*
        stage('Ejecutar SSH validar y permitir conexion a nuevo host') {
            steps {
                script {
                    sh "chmod 400 Users/isaacbarrera/Downloads/terraform.pem"
                    def SSH_KEY = input(
                        message: 'Lab IaC:Ingrese la ruta del doc .pem',
                        parameters: [string(name: 'SSH_KEY', defaultValue: '')]
                    )
                    def IP_ADDRESS = input(
                        message: 'Lab IaC:Ingrese el ip de la instancia',
                        parameters: [string(name: 'IP_ADDRESS', defaultValue: '')]
                    )
                    sh "ssh -i '${SSH_KEY}' ec2-user@'${IP_ADDRESS}'"
                }
            }
        }
        */
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