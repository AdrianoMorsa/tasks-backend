pipeline {
    agent any
    stages {
        stage ('Buld Backend'){
            steps {
                shell 'mvn clean package -DskipTests=true'
            }
        }
        stage ('Unit Tests'){
            steps {
                shell 'mvn test'
            }
        }
        stage ('Sonar Analysis') {
            environment {
                scannerHome = tool 'SONAR_SCANNER'
            }
            steps {
                withSonarQubeEnv('SONAR_LOCAL') {             
                    shell "${scannerHome}/bin/sonar-scanner -e -Dsonar.projectKey=DeployBack -Dsonar.host.url=http://localhost:9000 -Dsonar.login=d011af7496dba36c009cb4ed206f0d573164de7a -Dsonar.java.binaries=target -Dsonar.coverage.exclusions=**/.mvn/**,**/src/test/**,**/model/**,**Application.java"
                }
            }
        }
    }
}


