pipeline {
    
    agent any
    
    stages {
        stage('Clone repo') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'ls -l'
                //sh 'cd flask/examples/tutorial'
                //sh 'python3 -m venv .venv'
                //sh '. .venv/bin/activate'
                //sh 'pip install -e ../..'
                //sh 'pip install -e .'
            }
        }
        //stage('Run') {
        //    steps {
        //        sh 'flask --app flaskr init-db'
        //        sh 'flask --app flaskr run --debug'
        //    }
        //}
    }
}