pipeline {
    
    agent any

    stages {

        stage('Build'){
            steps {
                sh "dotnet build pipelines-dotnet-core.csproj"
                  }
        }

        stage('Test'){
            steps {
                
                sh "dotnet add package JUnitTestLogger --version 1.1.0"
                sh 'dotnet test pipelines-dotnet-core.csproj --logger "junit;LogFilePath=./test/results.xml"'
                sh "ls -lA ./test"
                //sh "dotnet test pipelines-dotnet-core.csproj"
            }

            //post {
            //    always {
            //        junit './test/results.xml'
            //    }
            //}
        }

        stage('Package1'){
            steps {
                
                sh "echo package"
            }
            //*post {
            //    success {
            //        archiveArtifacts artifacts: '**/target/*.war', followSymlinks: false
            //    }
            //}*/
        }
    }
}
