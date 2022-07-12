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
                sh 'dotnet test pipelines-dotnet-core.csproj --logger "junit;LogFilePath=**/test/TEST-*.xml"'
                  }

            post {
                always {
                    junit '**/test/TEST-*.xml'
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
