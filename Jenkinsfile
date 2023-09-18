stage('Instalar paquete en EC2') {
    steps {
        script {
            def targetHost = input(
                message: 'Lab IaC: 44.215.121.231',
                parameters: [string(name: 'targetHost', defaultValue: '44.215.121.231')]
            )

            sh "/usr/local/bin/ansible-playbook -i '${targetHost},' /usr/local/bin/ansible/playbooks/install_app.yml -e 'target_host=${targetHost}'"
        }
    }
}
