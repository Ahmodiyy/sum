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
    }
}