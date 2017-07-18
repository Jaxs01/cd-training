node {
    try {
        stage('Build') {
            git 'git@bitbucket.org:Assurity/cd-training.git'
            sh  './gradlew clean build'
        }
    } finally {
        publishHTML([allowMissing: true, alwaysLinkToLastBuild: true, keepAll: true, reportDir: 'build/reports/spec', reportFiles: 'CricketSpec.html', reportName: 'Cricket Specification', reportTitles: 'Cricket Specification'])
    }
    stage('Results') {
        junit '**/build/test-results/test/TEST-*.xml'
        archive 'build/libs/*.jar'
    }
}