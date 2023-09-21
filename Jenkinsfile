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
                    //sh "/usr/local/bin/ansible-playbook -i '${targetHost},' playbooks/install_app.yml -e 'target_host=${targetHost}'"
                    sh "/usr/local/bin/ansible-playbook -i '${targetHost}' '${targetHost}'/install_app.yml"
                }
            }
        }
    }
}