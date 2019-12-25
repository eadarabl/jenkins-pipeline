# jenkins-pipeline
node{
    def mvnHome = tool name: 'maven3', type:'maven'
    stage('SCM Checkout'){
       git credentialsId: 'github', url: 'https://github.com/javahometech/6pmwebapp' 
       
    }
    stage('Maven Build'){
        
       sh script:"${mvnHome}/bin/mvn clean package"
       }
}
