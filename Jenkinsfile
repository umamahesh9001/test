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
		       mvn clean package
		     }
             }               
        }
}
