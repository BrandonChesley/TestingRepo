#!groovy
node('EmrDevBuildWin') {
    stage('Create Files'){
        bat ''' echo TestFile1 > Testfile1.txt
           	echo TestFile2 > Testfile2.txt
                echo TestFile3 > Testfile3.txt
            '''
    }
    stage('Test Git Push'){
		git url: "ssh://jenkins@your-git-repo:12345/your-git-project.git",
    			credentialsId: 'jenkins_ssh_key',
    			branch: 'develop'
		bat
	    		'''
			git tag Test_Tag
			git add .
			git commit -m "Test"
			git push
			'''
    }
}
