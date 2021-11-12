pipeline{
    agent any
    stages{
        stage("Cloine Git"){
            git branch: 'main', credentialsId: 'BitBucketUser', url: 'https://github.com/vprasadk111/Ansible_CopyShellFetch.git'
        }
    }
}
