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
		       bat 'mvn clean deploy -Dmule.home = D:/Mahesh/mule/mule'
		     }
             }               
        }
}
