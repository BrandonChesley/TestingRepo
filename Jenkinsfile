#!groovy
node('EmrDevBuildWin') {
    
    stage('Checkout'){
        checkout scm   
    }
    stage('Create Files'){
        bat 'echo TestFile1 > Testfile1.txt'
        bat 'echo TestFile2 > Testfile2.txt'
        bat 'echo TestFile3 > Testfile3.txt'
    }
    stage('Test Git Push'){
        bat 'git tag Test_Tag'
        bat 'git add .'
        bat 'git push'
        
    }
}
