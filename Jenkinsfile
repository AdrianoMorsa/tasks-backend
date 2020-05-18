pipeline {
    agent any
    stages {
        stage ('Buld Backend'){
            steps {
                shell 'mvn clean package -DskipTests=true'
            }
        }
    }
}
##