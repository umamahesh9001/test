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
			       step {
				   def mavenPOM = readMavenPom 'pom.xml'
				   }
				   step {
				   def nexusRepoName = mavenPOM.version.endsWith('SNAPSHOT') ? 'uca-snapshots' : 'uca-release'
				   }
				   nexusArtifactUploader artifacts : [
					   [
							artifactId : 'test',
							classifier: '',
							file: '/target/test-1.0.0-${mavenPOM.version}-mule-application.jar',
							type: 'jar'
					   ]
				   ],
				   credentialsId : 'nexusCred',
				   groupId : 'com.mycompany',
				   nexusUrl : 'localhost:8090/nexus',
				   nexusVersion : 'nexus2',
				   protocol : 'http',
				   repository : nexusRepoName,
				   version : '${mavenPOM.version}'
				
			   
			   
		     }
        } 
    }
}
