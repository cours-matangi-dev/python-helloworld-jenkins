pipeline {
    agent any 
    stages {
        stage('clone') { 
            steps {
                sh "rm -rf *"
                sh "git clone https://github.com/cours-matangi-dev/python-helloworld-jenkins.git"
            }
        }
        stage('run') { 
            steps {
                sh "cd python-helloworld-jenkins && python3 script.py"
            }
        }
        stage('test') { 
            steps {
                sh 'cd python-helloworld-jenkins && if [[ "$(cat test.file | grep hello | wc -l)" == "1" ]]; then echo "OK"; else echo "not OK"; fi'
            }
        }
    }
}
