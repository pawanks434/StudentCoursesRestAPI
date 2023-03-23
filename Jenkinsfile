pipeline {
    agent any
        triggers { pollSCM('* 11 * * 1-5') }
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
            sh 'echo docker scan shaikkhajaibrahim/spc:latest'    
            sh 'docker image push pawanks434/spc:latest'
            
            }
        }
        
    }
}