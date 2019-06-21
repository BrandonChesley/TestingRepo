!#groovy
node('EmrDevBuildWin'){
	stage('Run Batch'){
		try{
			withCredentials([usernamePassword(credentialsId: '64c037fc-0032-4d4c-b6ee-7cd06ee4ec27', passwordVariable: 'svn_pass', usernameVariable: 'svn_user')]) {
				bat '''C:/Users/jenkins/MonitorChanges/MonitorChanges.bat "$svn_user" "$svn_pass" '''
			}
			
