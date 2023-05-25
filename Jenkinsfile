pipeline {
    
    agent any
    tools{
        nodejs "node"
    }

    stages{
        
        stage("Clone"){
            steps{
                
                git 'https://github.com/ManyweleMike/gallery'
            }
        }
        stage("build"){
            steps{
                echo'Building the application'
                sh 'npm install'
            }
        }

        stage("test"){
            steps{
                echo'testing the application..'
                sh 'npm test'
            }
        }
    }

}