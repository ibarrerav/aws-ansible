stage('Instalar paquete en EC2') {
    steps {
        script {
            def targetHost = input(
                message: 'Ingresa el nombre o IP de la instancia EC2:',
                parameters: [string(name: 'targetHost', defaultValue: '44.215.121.231')]
            )

            sh "ansible-playbook -i '${targetHost},' playbooks/install_app.yml -e 'target_host=${targetHost}'"
        }
    }
}
