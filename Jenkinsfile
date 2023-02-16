pipeline {
agent any
stages {
    stage('Build') {
        steps {
            sh 'g++ -o pes2ug20cs472-1 hello.cpp'
        }
    }
    
    stage('Test') {
        steps {
            sh './pes2ug20cs472-1'
        }
    }
    
    stage('Deploy') {
        steps {
            // deployment code
            sh 'mvn deploy'
            echo 'deployment successful'
        }
    }
}

post {
    always {
        script {
            if (currentBuild.result == "FAILURE") {
                echo "Pipeline failed"
            }
        }
    }
}
}
