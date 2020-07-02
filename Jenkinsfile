pipeline 
{
  agent any
  tools 
  { 
    maven 'MAVEN_HOME'
  }
  stages 
	{
        stage ('Compile and deploy to Mule Server') 
	    {
		    steps
		     {
		       bat 'mvn clean deploy -DmuleDeploy -Dmule.home=D:/Mahesh/mule/mule'
		     }
        }

		stage ('Publish the artifact to Nexus repository') 
	    {
		    steps
		     {
		       nexusArtifactUploader artifacts : [
				   [
						artifactId : 'test',
						classifier: '',
						file: 'C:/Program Files (x86)/Jenkins/workspace/practice_1_pipeline/target/test-1.0.0-mule-application.jar',
						type: 'jar'
				   ]
			   ],
			   credentialsId : 'nexusCred',
			   groupId : 'com.mycompany',
			   nexusUrl : 'localhost:8090/nexus',
			   nexusVersion : 'nexus2',
			   protocol : 'http',
			   repository : 'http://localhost:8090/nexus/content/repositories/releases',
			   version : '1.0.0'
			   
			   
		     }
        } 
    }
}
