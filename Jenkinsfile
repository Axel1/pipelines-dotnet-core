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
                
                sh "dotnet test pipelines-dotnet-core.csproj"
            }

            //post {
            //    always {
            //        junit '**/target/surefire-reports/TEST-*.xml'
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
