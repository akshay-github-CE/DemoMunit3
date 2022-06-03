pipeline
{
    agent any
    
    stages{
    
        stage('Build Application'){
        steps{
        bat 'mvn clean package -DskipTests'
        }	
        }
        
        stage('Munit Testing'){
        steps{
        bat 'mvn clean test'
        }     
        }
             
        stage('Deploy Application To Mulesoft'){
        steps{
        bat 'mvn package deploy -DmuleDeploy -Danypoint.userName=OssomVictory5 -Danypoint.password=Capg@1999'
        }
       
        }
       
   
    }
}
