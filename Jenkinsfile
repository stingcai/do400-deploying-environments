pipleine {
    agnet {
        node{
            label 'maven'
        }
    }

    stages {
        stage('Test') {
            steps {
                sh './mvnw clean test'
            }
        }
        
        stage('Package') {
            steps {
                sh '''
                ./mvnw package -DskipTests \
                -Dquarkus.package.type=uber-jar
                '''
                archiveArtifacts 'taget/*.jar'
            }
        }
    }
}