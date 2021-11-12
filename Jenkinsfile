pipeline{
    agent any
    stages{
        stage("Cloine Git"){
            steps{
                git branch: 'main', credentialsId: 'BitBucketUser', url: 'https://github.com/vprasadk111/Ansible_CopyShellFetch.git'
            }
        }
        stage("Run ansible playbook"){
            steps{
                sh 'ansible-playbook -i inventory.txt copy_shell_fetch.yml'
            }
        }
    }
}
