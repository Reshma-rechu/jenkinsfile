node {
   stage('creating workspace directory') 
       sh "mkdir hello_app"
   
   stage('checkout to sub-directory') 
       checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'hello_app']], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Reshma-rechu/JenkinsDemo.git']]])
   
   stage('checkout') 
       checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Reshma-rechu/JenkinsDemo.git']]])
   
}
 
