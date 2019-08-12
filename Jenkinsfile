#!groovy
node('EmrDevBuildWin') {
	stage('Checkout'){
		checkout scm
	}
	
    stage('Create Files'){
        bat ''' echo TestFile1 > Testfile1.txt
           	echo TestFile2 > Testfile2.txt
                echo TestFile3 > Testfile3.txt
            '''
    }
    stage('Test Git Push'){
	    sshagent(['01b4666e-9b05-47c2-b0e5-407c308c7e1e']) {
			bat
					'''
				git tag Test_Tag
				git add .
				git commit -m "Test"
				git push
				'''
		}
    }
}
