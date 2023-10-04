pipeline{
	agent any 
	stages{
		stage('clonecode'){
			steps{
				checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'team7-git-id', url: 'https://github.com/Etech-Team-007/gear.git']])
			}
		}
		stage('artifactbuild'){
			steps{
				sh "df -h"
				sh 'pwd'
				sh "whoami"
			}
		}
		stage('unitest'){
			steps{
				sh "lsblk"
			}
		}
		stage('maintenance'){
			steps{
				sh "lscpu"
			}
		}
		stage('security_check'){
			steps{
				sh 'bash -x /var/lib/jenkins/workspace/jenkins-second-pipeline.pipeline.sh'
			}
		}
	}
}