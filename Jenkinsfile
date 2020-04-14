pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
        stage('Deploy'){
            steps {
                timeout(time: 5, unit: 'MINUTES'){
                    retry(3){
                        sh './flakey-deploy.sh'
                    }
                }
            }
        }
    }
}
