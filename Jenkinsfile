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
        stage('Deploy to Heroku') {
           steps {
              withCredentials([usernameColonPassword(credentialsId: 'hheroku3', variable: 'HEROKU_CREDENTIALS' )]){
              sh 'git push https://${HEROKU_CREDENTIALS}@https://git.heroku.com/infinite-thicket-33495.git master'
             }
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