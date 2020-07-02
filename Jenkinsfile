pipeline 
{
  agent any
  tools 
  { 
    maven 'MAVEN_HOME'
  }
  stages 
	{
           stage ('Compile Stage') 
	    {
		     steps
		     {
		       sh script : 'mvn clean package'
		     }
             }               
        }
}
