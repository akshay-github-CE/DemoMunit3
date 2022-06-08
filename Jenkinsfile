pipeline
{
    agent any
    
    stages{
        
        stage('SonarQube analysis') {
            steps {
            withSonarQubeEnv('SonarQube') {
            bat 'mvn sonar:sonar -Dsonar.sources=src/ -Dsonar.host.url=http://localhost:9000 -Dsonar.login=802e819dd1c88aa5eb4814915c233e9998aa48e6'
            }
            }
            }
       
        
        stage("Quality gate") {
            steps {
            waitForQualityGate abortPipeline: true
            }
            }
    
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
