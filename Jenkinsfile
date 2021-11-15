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
                ansiblePlaybook credentialsId: 'ec2-user', disableHostKeyChecking: true, installation: 'ansible', inventory: 'inventory.txt', playbook: 'copy_shell_fetch_Mail.yml'
            }
        }
    }
post {
        always {
           emailext (attachLog: true, body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}", subject: 'Test', to: 'vishnumanohar.111@gmail.com')

        }
}
}
