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
		       bat 'mvn clean deploy -DmuleDeploy -Dmule.home=D:\Mahesh\mule\mule'
		     }
             }               
        }
}
