pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }

        stage('Release tag') {
            environment {
                GIT_TAG = "Version-1.$BUILD_NUMBER"
            }
            steps {
                sh 'git config user.name "Tharindu"'
                sh 'git config user.email "perera.tharindu29@gmail.com"'

                sh 'git tag -a $GIT_TAG -m "[Jenkins CI] New Tag"'
                sh 'git push origin $GIT_TAG'
            }
        }
    }
}
