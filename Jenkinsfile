pipeline {
    agent { label 'JAVA_NEWNODE' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/praneeth6242/StudentCoursesRestAPI.git',
                    branch: 'release'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t chowdarybtc/spc:latest .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'echo docker scan chowdarybtc/spc:latest'
                sh 'docker image push chowdarybtc/spc:latest'
            }
        }
    }

}