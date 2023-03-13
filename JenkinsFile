pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/auto.txt'
                sh 'echo "chassis" > build/auto.txt' 
                sh 'echo "motore" >> build/auto.txt' 
                sh 'echo "carrozzeria" >> build/auto.txt' 
            }
        }
        stage('Test') {
            steps {
                sh 'test -f build/auto.txt'
                sh 'grep "chassis" build/auto.txt'
                sh 'grep "motore" build/auto.txt'
                sh 'grep "carrozzeria" build/auto.txt'
                
            }
        }
        stage ('Publish'){
            steps{
                archiveArtifacts artifacts: 'build/'
            }
        }
    }
}
