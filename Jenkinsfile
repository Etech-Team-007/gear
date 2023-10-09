pipeline{
	agent any 
	stages{
		stage('clonecode'){
			steps{
				checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'team-7', url: 'https://github.com/Etech-Team-007/team7app.git']])
			}
		}
		stage('artifactbuild'){
			agent {label'slave1'}
			steps{
				sh "df -h"
				sh 'pwd'
				sh "whoami"
			}
		}
		stage('parallel'){
			agent {label'slave2'}
		parallel{
		stage('unitest'){
			steps{
				sh "lsblk"
				sh "logname"
				sh "id"
			}
		}
		stage('deployment'){
			steps{
				sh "lscpu"
			}
		}
			}
		}
		stage('security_check'){
			agent {label'slave1'}
			steps{
				sh 'bash -x /var/lib/jenkins/workspace/jenkins-second-pipeline/pipeline.sh'
			}
		}
	}
}