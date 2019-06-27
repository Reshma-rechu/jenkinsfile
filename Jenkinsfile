node {
   stage('creating workspace directory') 
       sh "mkdir hello_app"
   
   stage('checkout to sub-directory') 
       checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'hello_app']], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Reshma-rechu/JenkinsDemo.git']]])
   
   stage('checkout') 
       checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Reshma-rechu/JenkinsDemo.git']]])
   
   stage('executing shell script')
       sh "chmod 755 hello.sh"
       sh "./hello.sh"
       sh "touch test1.txt"
       sh "touch test2.txt"
	   
   stage('archiving files')
       archiveArtifacts '*.txt'
	   
   stage('listing workspace')
       sh "tree hello_app"
       sh "tree /var/lib/jenkins/workspace/jenkinsfile"
       
   stage('build status')
         echo "Build ${currentBuild.currentResult}"
   
}

