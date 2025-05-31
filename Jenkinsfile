pipeline {
    
    agent any

    environment {
        WORKDIR = 'examples/tutorial'
    }
    
    stages {
        stage('Clone repo') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                dir("${WORKDIR}") {
                    sh '''
                        python3 -m venv venv
                        . venv/bin/activate
                        pip install .
                    '''
                }
            }
        }
        stage('Run') {
            steps {
                dir("${WORKDIR}") {
                    sh '''
                        . venv/bin/activate
                        flask --app fleskr init-db
                        flask --app fleskr run --debug
                    '''
                } 
            }
        }
    }

}