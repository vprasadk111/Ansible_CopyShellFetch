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
           emailext (attachLog: true, body: "<b>Build URL :</b> ${env.BUILD_URL} <br><b>Build Workspace :</b> ${env.WORKSPACE} <br> <b>Build Result :</b> ${currentBuild.result}", subject: "Status of pipeline: ${currentBuild.fullDisplayName}", to: 'vishnumanohar.111@gmail.com')
        }
}
}
