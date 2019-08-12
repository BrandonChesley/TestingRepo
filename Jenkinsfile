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
        bat ''' 
                git config --global user.email "jenkins@emrdevbuildwin.QuadrantHR.com"
                git config --global user.name "Jenkins Release (${BUILD_NUMBER})"
                git tag Test_Tag
                git add .
                git commit -m "Test"
                git push origin HEAD:develop --tags
            '''
        
    }
}
