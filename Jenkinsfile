pipeline {
            agent any
            stages {
                    stage ('Compile Stage') {
                    
                        steps{
                          
                                  withMaven( maven : 'MAVEN_HOME') {
                                            sh 'mvn clean package'
                                  }
                        }
                            
                    }
                    stage ('Deploy Stage') {
                    
                        steps{
                          
                                  withMaven( maven : 'MAVEN_HOME') {
                                            sh 'mvn deploy'
                                  }
                                  
                        }
                            
                    }
            }
}
