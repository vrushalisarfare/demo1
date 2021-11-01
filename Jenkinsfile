node{
  stage{'SCM Checkout'){
       git 'https://github.com/vrushalisarfare/javaloginapp'
       }
  stage ('Compile-Package'){
    def mvnHome = tool name: 'maven-3' , type: 'maven'
    sh "${mvnHome}/bin/ mvn package"
  }
  
  stage ('SonarQube Analysis'){
    def mvnHome = tool name: 'maven-3', type: 'maven'
    withSonarQubeEnv('sonarqube-9.1'){
      sh "${mvnHome}/bin/mvn sonar:sonar"
    }
  }
       }
    
