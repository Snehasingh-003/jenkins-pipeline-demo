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
        echo "Building the project..."
        sh 'echo "Scripted build executed" > scripted-build.txt'
    }

    stage('Echo Build Status') {
        echo "Build finished successfully!"
    }

    stage('Archive Artifacts') {
        archiveArtifacts artifacts: 'scripted-build.txt', fingerprint: true
    }
}
