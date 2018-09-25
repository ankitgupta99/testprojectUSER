pipeline {
    agent any
    stages{
		stage{('Clone sources') {
			steps{
			git url: 'https://github.com/jeettest2/testprojectUSER.git'
							}	
						}

		stage('Artifactory configuration') {
		steps{
        // Tool name from Jenkins configuration
        rtMaven.tool = "Maven-3.3.9"
        // Set Artifactory repositories for dependencies resolution and artifacts deployment.
        rtMaven.deployer releaseRepo:'libs-release-local', snapshotRepo:'libs-snapshot-local', server: server
        rtMaven.resolver releaseRepo:'libs-release', snapshotRepo:'libs-snapshot', server: server
								}
						}

		stage('Maven build') {
		steps{
        buildInfo = rtMaven.run pom: 'pom.xml', goals: 'clean install'
		}
    }
		stage('Publish build info') {
		steps{
        server.publishBuildInfo buildInfo
		}
		}
		}
	}
	}
