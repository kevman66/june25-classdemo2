pipeline{
    agent any
    environment {
        VENV = 'venv'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/kevman66/june25-classdemo2.git' // Specify your repository URL here
            }
        }
        stage('Setup Virtual Environment') {
            steps {
                sh'''
                    python3 -m venv $VENV
                    . $VENV/bin/activate
                    pip install -r requirements.txt
                '''
            }
        }
        stage('Run Tests') {
            steps {
                sh'''
                    . $VENV/bin/activate
                    pytest tests/
                '''
            }
        }
    }

}