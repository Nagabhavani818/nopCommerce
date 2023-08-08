pipeline {
    agent { label 'NOP'}
    triggers {
        pollSCM('* * * * * ')
    }
     tools {
        jdk JDK-17 
    }
    stages { 
        stage('git') {
            steps {
                git branch: 'develop',
                    url: 'https://github.com/Nagabhavani818/nopCommerce.git'
               
            }
        }
        stage('restore and build') {
            steps {
                sh: '''dotnet restore src/NopCommerce.sln ,
                    dotnet build -c Release src/NopCommerce.sln'''
            }
        }
    }
}
