pipeline 
{
  agent any
  tools 
  { 
    maven 'MAVEN_HOME'
  }
  stages 
	{
		stage ('go to path') {
			script {
				bat 'cd C:/Program Files (x86)/Jenkins/workspace/practice_1_pipeline' 
			}
		}
        stage ('Compile and deploy to Mule Server') 
	    {
		    script
		     {    
			  
			  bat 'mvn clean deploy -DmuleDeploy -Dmule.home=D:/Mahesh/mule/mule'     
		     }
        }

		stage ('Publish the artifact to Nexus repository') 
	    {
		    steps
		     {
			  script {
			       
				   def mavenPOM = readMavenPom file : 'pom.xml'
				   def nexusRepoName = mavenPOM.version.endsWith('SNAPSHOT') ? 'uca-snapshots' : 'uca-release'
				   // def jenkinsPath = workspace
				   // echo ${mavenPOM.version} , 
				   nexusArtifactUploader artifacts : [
					   [
							artifactId : 'test',
							classifier: '',
						   file: "/target/test-${mavenPOM.version}-mule-application.jar",
							type: 'jar'
					   ]
				   ],
				   credentialsId : 'nexusCred',
				   groupId : 'com.mycompany',
				   nexusUrl : 'localhost:8090/nexus',
				   nexusVersion : 'nexus2',
				   protocol : 'http',
				   repository : nexusRepoName,
				   version : "${mavenPOM.version}"
				
				}
			   
		     }
        } 
    }
}
