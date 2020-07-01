pipeline {
            agent any
            tools {
                    maven 'MAVEN_HOME'
        
    }
            stages {
                    stage ('Compile Stage') {
                    
                        steps{
                          
                                 
                                            sh 'mvn clean package'
                                 
                        }
                            
                    }
                    stage ('Deploy Stage') {
                    
                        steps{
                          
                                 
                                            sh 'mvn deploy'
                                  
                                  
                        }
                            
                    }
            }
}
