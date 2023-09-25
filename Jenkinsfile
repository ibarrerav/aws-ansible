pipeline {
    agent any

    stages {
        /*
        stage('Mover archivo .pem de local a Docker') {
            steps {
                script {
                    def rutaLocal = input(
                        message: 'Lab IaC:Ingrese la ruta local del .pem',
                        parameters: [string(name: 'rutaLocal', defaultValue: '')]
                    )
                    def nombreContenedor = input(
                        message: 'Lab IaC:Ingrese el nombre del contenedor',
                        parameters: [string(name: 'nombreContenedor', defaultValue: '')]
                    )
                    def rutaContenedor = input(
                        message: 'Lab IaC:Ingrese la ruta del contenedor',
                        parameters: [string(name: 'rutaContenedor', defaultValue: '')]
                    )
                    sh "docker cp '${rutaLocal}' '${nombreContenedor}:${rutaContenedor}'"
                    sh "chmod 400 '${rutaContenedor}'/terraform.pem"
                }
            }
        }
        stage('Ejecutar SSH validar y permitir conexion a nuevo host') {
            steps {
                script {
                    def SSH_KEY = input(
                        message: 'Lab IaC:Ingrese la ruta del doc .pem',
                        parameters: [string(name: 'SSH_KEY', defaultValue: '')]
                    )
                    def IP_ADDRESS = input(
                        message: 'Lab IaC:Ingrese el ip de la instancia',
                        parameters: [string(name: 'IP_ADDRESS', defaultValue: '')]
                    )
                    sh "ssh -i '${SSH_KEY}' 'ec2-user@${IP_ADDRESS}'"
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