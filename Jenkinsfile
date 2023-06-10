pipeline {
		agent {
			label {
			label "jnlp"
			customWorkspace "/mnt/gol" 
			}
		}
		stages {
			stage ("stage-1") {
					steps {
						sh "rm -rf /mnt/gol/*"
						sh "git clone https://github.com/sushil-11-jadhav/gameoflife1.git"
						
					dir ("/mnt/gol/gameoflife1") {
						sh "mvn clean install"
						sh "cp gameoflife-web/target/gameoflife.war /mnt/apache-tomcat-9.0.74/webapps"
						sh "sh /mnt/apache-tomcat-9.0.74/bin/startup.sh"
					}
					
				}
			}
			
		}
}		
