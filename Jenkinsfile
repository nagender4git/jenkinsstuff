node('JenkinsNode') {

	def workspace = pwd()
	echo workspace
   
      
        stage('Clean Workspace'){
           // echo 'Cleaning everything in the workspace directory:  ${env.WORKSPACE}'
           cleanWs()
		   ws(workspace+'/resources') {
				 git credentialsId: '00af7364-a9f5-47c3-b4f9-eb5f727e1aa6', url: 'https://github.com/nagender4git/jenkinsstuff.git'
			}
			
		}
          
		 
		 stage ('Tools Set up'){
             echo 'Tools set up'
			 
			
         }
		 stage('Source Code Check out'){
		 ws(workspace+'/sourcecode') {
		      git credentialsId: '00af7364-a9f5-47c3-b4f9-eb5f727e1aa6', url: 'https://github.com/nagender4git/nagacode.git'
			  }
          
            echo 'Check out'
        }
        
          stage('Build'){
           sh '''
              export M2_HOME=/home/ec2-user/apache-maven-3.2.1
			  export M2=$M2_HOME/bin
			  export PATH=$M2:$PATH
			mvn -f resources/pom.xml clean package
		  
		   '''
		
}	 
        
        
  
        
 
    
}
