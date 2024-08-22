pipeline {
    agent any

    stages {
        stage('Deploy and Run Python App') {
            steps {
                script {
                    // Step 1: Deploy Python application to Ansible node
                    ansiblePlaybook(
                        playbook: 'deploy_python_app.yml',
                        inventory: 'inventory.ini',
                        extras: '-e "python_app=hello.py"'
                    )

                    // Step 2: Run Python application on Ansible node
                    ansiblePlaybook(
                        playbook: 'deploy_python_app.yml',
                        inventory: 'inventory.ini',
                        extras: '-e "python_app=hello.py"'
                    )
                }
            }
        }
    }
}
