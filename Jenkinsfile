pipeline {
    agent any
        triggers { pollSCM('* * * * *') }
    stages {
        stage('vcs') {
            steps {
                 git url: 'https://github.com/pawanks434/StudentCoursesRestAPI.git',
                 branch: 'develop'
            }
        }
        stage('build') {
            steps{
                 sh 'docker image build -t pawanks434/spc:latest . '
            }
        }
        stage('scan and push') {
            steps {
            sh 'docker image push pawanks434/spc:latest'
            }
        }
        
    }
}