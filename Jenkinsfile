pipeline{
    agent any
        triggers {
	pollscm('*/5 * * * *')
    }	
    stages{
       stage('SCM Checkout'){
         
       }
       stage('Gradle Package'){
       	   steps{
       	      echo 'Gradle Package'
       		 script{
       		    def grdlHome = tool name: 'Gradle', type: 'gradle'
       		    bat "gradlew build"
       			//def grdlHome = tool name: 'MAVEN_HOME', type: 'maven'
       			//echo "Gradle Home ${grdlHome}"
       			//def mvnCMD = "${mvnHome}/bin/mvn"
       			//echo "MVN CMD  ${mvnCMD}"
       			//bat "${mvnCMD} clean install"
       		 }
       	   }
       }
	   stage('compile'){
          steps{
           echo 'compiling the application'
         }
       }
       stage('build'){
          steps{
           echo 'building the application'
         }
       }
       stage('test'){
          steps{
           echo 'testing the application'
          }
       }
       stage('deploy'){
          steps{
            echo 'deploying the application'
        }
      }
	stage('deploy to k8s'){
          steps{
            echo 'deploying the application on k8s'
        }
      }    
    }
	post{
		always{
			echo 'this is samara'
		}
		success{
			echo 'this will run success'
		}
		failure{
			echo 'this will run failure'
		}
		unstable{
			echo 'this will run unstable'
		}
		changed{
			echo 'this will run changed'
		}
	}
}
