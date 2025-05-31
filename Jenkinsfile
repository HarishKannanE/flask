pipeline {
    
    agent any

    environment {
        VENV_PATH = 'venv'
        FLASK_APP = 'flaskr'
        WORKDIR = 'example/tutorial'
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
                        python3 -m venv ${VENV_PATH}
                        . ${VENV_PATH}/bin/activate
                        pip install .
                    '''
                }
            }
        }
        stage('Run') {
            steps {
                dir("${WORKDIR}") {
                    sh '''
                        . ${VENV_PATH}/bin/activate
                        export PYTHONPATH=$PWD/examples/tutorial
                        cd examples/tutorial
                        flask --app ${FLASK_APP} init-db
                        flask --app ${FLASK_APP} run --debug
                    '''
                } 
            }
        }
    }

}