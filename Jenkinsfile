node {

    properties([
        pipelineTriggers([
            cron('H/5 * * * *'),
            pollSCM('H/2 * * * *')
        ])
    ])

    stage('Clone Repository') {
        git 'https://github.com/Snehasingh-003/jenkins-pipeline-demo.git'
    }

    stage('Build') {
        echo "Compiling Java file..."
        bat 'javac Test.java'
    }

    stage('Run Program') {
        bat 'java Test > output_scripted.txt'
    }

    stage('Echo Build Status') {
        echo "Scripted Pipeline Build Completed!"
    }

    stage('Archive Artifacts') {
        archiveArtifacts artifacts: 'output_scripted.txt', fingerprint: true
    }
}
