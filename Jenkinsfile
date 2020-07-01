pipeline {
            agent any
            stages {
                    stage ('Compile Stage') {
                          
                          withMaven( maven : 'MAVEN_HOME') {
                                    sh 'mvn clean package'
                          }
                            
                    }
                    stage ('Deploy Stage') {
                          
                          withMaven( maven : 'MAVEN_HOME') {
                                    sh 'mvn deploy'
                          }
                            
                    }
            }
}
