pipeline {
            agent any
            tools {
                    maven 'Maven 3.3.5'
        
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
