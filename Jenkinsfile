tools {
    maven 'Maven-3'
}

stages {
    stage('Checkout') {
        steps {
            git branch: 'main',
                url: 'https://github.com/your-org/your-repo.git'
        }
    }

    stage('Build') {
        steps {
            sh 'mvn clean compile'
        }
    }

    stage('Test') {
        steps {
            sh 'mvn test'
        }
    }

    stage('Package') {
        steps {
            sh 'mvn package -DskipTests'
        }
    }
}

post {
    success {
        echo 'Build succeeded!'
        archiveArtifacts artifacts: 'target/*.jar'
    }
    failure {
        echo 'Build failed!'
    }
    always {
        echo 'Pipeline complete.'
    }
}