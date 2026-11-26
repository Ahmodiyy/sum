 pipeline {
    agent any
    stages {
        stage("Checkout") {
            steps {
                git url:'https://github.com/Ahmodiyy/sum.git', branch:'main'
            }
        }
        stage("Compile") {
            steps {
                bat "./gradlew compileJava"
            }
        }
        stage("Test") {
            steps {
                bat "./gradlew test"
            }
        }
        stage("Code Coverage") {
            steps {
                sh "./gradlew jacocoTestReport"
                publishHTML(target: [
                    allowMissing: false,
                    alwaysLinkToLastBuild: false,
                    keepAll: true,
                    reportDir: 'build/reports/jacoco/test/html',
                    reportF:iles: 'index.html',
                    reportName: 'JaCoCo Report'
                ])
                sh "./gradlew jacocoTestCoverageVerification"
            }
        }
    }
}