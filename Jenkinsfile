pipeline{
 agent any
 environment {
    ANYPOINT = credentials('ANYPOINT')
 }
 stages {
 	stage ('Build'){
 		steps {
 			withMaven(maven:'maven'){
 				sh 'mvn -f openweather-api-impl/pom.xml clean install'
 			}
 		}
 	}
 	stage ('Deploy'){
 		steps {
 			withMaven(maven:'maven'){
 				sh 'mvn -f openweather-api-impl/pom.xml package deploy  -Dusername=joydeep_010 -Dpassword=Joy@1994 -Denvironment=Sandbox -DmuleDeploy'
 			}
 		}
 	}
 }

}