pipeline{
		agent any
		stages{
		   		stage(clean){
				steps{
					sh 'mvn clean'
					}
			}
			
			stage(install){
			steps{
				sh 'mvn  install -DskipTests'
				}
			}
			
			stage(test){
				steps{
					sh 'mvn clean install -DskipTests'
				}
				
					
					post {
  				always {
   				 archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
					
					 }
				}
			}
		}
	}
