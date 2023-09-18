stage('Instalar paquete en EC2') {
    steps {
        script {
            def targetHost = input(
                message: 'Ingresa el nombre o IP de la instancia EC2:',
                parameters: [string(name: 'targetHost', defaultValue: '')]
            )

            sh "ansible-playbook -i '${44.215.121.231},' playbooks/install_app.yml -e 'target_host=${44.215.121.231}'"
        }
    }
}

