node('JenkinsNode') {

	def workspace = pwd()

        echo env.BRANCH_NAME
   
	echo workspace
 	//def props = readFile '/properties/sample.properties'
	//echo props['name']
    def EMS_INGESTION_SERVICE_HOST = '10.152.140.22'
    def EMS_TAG_VERSION = '2.2'
    def EMS_USER = 'root'
    def EMS_HOST = '10.152.140.22'
    def DOCKER_REGISTRY_IP = '10.152.143.51'
    def DOCKER_REGISTRY_PORT = '5000'
    def DOCKER_REGISTRY_PATH = 'vcs_ems'
    def EMS_QUERY_SERVICE_TAG_NAME = 'vcs-ems-queryservice'
    def EMS_INGEST_SERVICE_TAG_NAME = 'vcs-ems-ingestservice'
    def EMS_NOTIF_SERVICE_SIMULATOR_TAG_NAME = 'vcs-ems-notifservicesimulator'
    def BUILD_N = '$BUILD_N'
    def COMPOSE_EMS_INGEST_SERVICE_TAG_NAME = 'vcsems_ingestionservice:latest'
    def COMPOSE_EMS_QUERY_SERVICE_TAG_NAME = 'vcsems_queryservice:latest'
    def COMPOSE_EMS_NOTIF_SERVICE_SIMULATOR_TAG_NAME = 'vcs-ems-notifservicesimulator:latest'
    def PG_PORT_5432_TCP_ADDR = '10.152.143.34'
    def PG_PORT_5432_TCP_PORT = '5432'

        
        stage('Clean Workspace'){
           // echo 'Cleaning everything in the workspace directory:  ${env.WORKSPACE}'
           cleanWs()
		   ws('sourcecode') {
				 git credentialsId: '00af7364-a9f5-47c3-b4f9-eb5f727e1aa6', url: 'https://github.com/nagender4git/jenkinsstuff.git'
			}
			dir("/home/ec2-user/workspace/full-flow/")
        }
         stage ('Tools Set up'){
             echo 'Tools set up'
			 
			
         }
		 stage('Check out'){
		      git credentialsId: '00af7364-a9f5-47c3-b4f9-eb5f727e1aa6', url: 'https://github.com/nagender4git/nagacode.git'
          
            echo 'Check out'
        }
        
          stage('Build'){
           sh '''
              export M2_HOME=/home/ec2-user/apache-maven-3.2.1
			  export M2=$M2_HOME/bin
			  export PATH=$M2:$PATH
			mvn clean package
		  
		   '''
		
}	 
        
        
  
        
 
    
}
