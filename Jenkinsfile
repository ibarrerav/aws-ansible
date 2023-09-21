pipeline {
    agent any

    stages {
        stage('Instalar paquete en EC2') {
            steps {
                script {
                    def targetHost = input(
                        message: 'Lab IaC:Ingrese su instancia',
                        parameters: [string(name: 'targetHost', defaultValue: '44.215.121.231')]
                    )
                    sh "/usr/local/bin/ansible-playbook -i '${targetHost},' playbooks/install_app.yml -e 'target_host=${targetHost}'"

                }
            }
        }

        stage('Deploy to EC2') {
            steps {
            script {
                // Copia tu clave SSH privada a una ubicación segura
                sh 'echo "$SSH_PRIVATE_KEY" > ~/.ssh/id_rsa'
                sh 'chmod 600 ~/.ssh/id_rsa'

                // Instala Ansible si no está instalado
                if ! command -v ansible &> /dev/null
                then
                    sh 'pip install ansible'
                fi

                // Ejecuta el playbook de Ansible
                sh 'ansible-playbook -i inventory.ini -u tu_usuario --private-key=~/.ssh/id_rsa miplaybook.yml'
                }
            }
        }
    }
}