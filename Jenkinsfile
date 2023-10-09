pipeline{
	agent{
		label 'slave1'
	} 
	stages{
		stage('1-clonecode'){
			steps{
				checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'jenkins7creds', url: 'https://github.com/Etech-Team-007/team7app.git']])
			}
		}
		stage('2-artifactbuild'){
			steps{
				sh "df -h"
				sh 'pwd'
				sh "whoami"
			}
		}
		stage('parallel'){
		parallel{
		stage('3-unitest'){
			steps{
				sh "lsblk"
				sh "logname"
				sh "id"
			}
		}
		stage('4-deployment'){
			agent{
				label 'slave2'
			}
			steps{
				sh "lscpu"
			}
		}
			}
		}
		stage('5-security_check'){
			agent{
				label 'slave1'
			}
			steps{
				sh 'echo "Guaranteed Offer Letter"'
			}
		}
	}
}