/* groovylint-disable CompileStatic */
pipeline {
    agent any
    environment {
        RELEASE = '20.04'
    }
    stages {
        stage('Build') {
            environment {
                LOG_LEVEL = 'INFO'
            }
            steps {
                echo "Building release $RELEASE with log level $LOG_LEVEL"
                writeFile file: 'test.txt', text: 'passed!'
            }
        }
    }
    post {
        success {
            archiveArtifacts 'test.txt'
        }
    }
}
