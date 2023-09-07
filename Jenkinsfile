pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // This step checks out your source code from the repository.
                // If your Jenkinsfile and Python script are in the same folder, it will be checked out here.
                checkout scm
            }
        }
        
        stage('Run Python Script') {
            steps {
                script {
                    // Assuming your Python script is named 'my_script.py'
                    def pythonScript = 'my_script.py'
                    
                    // Execute the Python script using the 'sh' step
                    // You may need to specify the Python interpreter if it's not in the PATH
                    sh "python ${pythonScript}"
                }
            }
        }
    }
    
    post {
        success {
            echo 'Python script ran successfully'
        }
        
        failure {
            echo 'Python script execution failed'
        }
    }
}
 
