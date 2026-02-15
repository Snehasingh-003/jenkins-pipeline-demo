pipeline {
    agent any

    triggers {
        pollSCM('H/2 * * * *')
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Snehasingh-003/jenkins-pipeline-demo.git'
            }
        }

        stage('Build') {
            steps {
                bat 'javac Test.java'
            }
        }

        stage('Run Program') {
            steps {
                bat 'java Test > output.txt'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'output.txt', fingerprint: true
            }
        }
    }
}
