pipeline {
    agent { label 'JDK' }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/dksinformations/MusicStore.git'
            } 
        }
        stage('build') {
            steps {
                sh 'dotnet restore ./MusicStore/MusicStore.csproj && dotnet build ./MusicStore/MusicStore.csproj'
            }
        }
        stage('test') {
            steps {
                sh 'dotnet build ./MusicStoreTest/MusicStoreTest.csproj'
            }

        }
    }
}