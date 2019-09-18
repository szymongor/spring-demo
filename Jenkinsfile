pipeline {
    agent any
        options {
        ansiColor('gnome-terminal')
        timestamps()
        timeout(5)
    }
    stages {
        stage('Preparation') {
            steps {
                git 'https://github.com/szymongor/spring-demo.git'
            }

        }
        stage('build') {
            steps {
                sh label: '', script: './mvnw clean package'
            }
        }
        stage('Results') {
            steps {
                junit '**/target/surefire-reports/TEST-*.xml'
                archiveArtifacts 'target/*.jar'
            }
        }
    }
}