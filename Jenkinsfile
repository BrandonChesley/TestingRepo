#!groovy
node('EmrDevBuildWin'){
	stage('Run Batch'){
		try{
			withCredentials([usernamePassword(credentialsId: '64c037fc-0032-4d4c-b6ee-7cd06ee4ec27', passwordVariable: 'svn_pass', usernameVariable: 'svn_user')]) {
				bat '''C:/Users/jenkins/MonitorChanges/MonitorChanges.bat %svn_user% %svn_pass% '''
			}
			def changedFiles = readFile "changedFileLocations"
			slackSend(
				teamDomain: 'qhr',
				tokenCredentialId: '77c778be-1124-423b-8aa3-ce1c7fdce4b3',
				channel: 'UJXPDG1V5',
				color: 'good',
				message: 'The follow files have been added or modified: \n' + changedFiles
			)
		}catch(err){
			throw(err)
		}		
	}
}
			
