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
                sh 'dotnet test --logger "junit;LogFilePath=./test/result.xml"'
                  }

            post {
                always {
                    junit './test/result.xml'
                }
            }
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
