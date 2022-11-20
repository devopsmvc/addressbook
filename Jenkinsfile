node{
    stage('code checkout'){
        git 'https://github.com/devopsmvc/addressbook.git'
    }
    
    stage('clean.. compile... test... package...'){
        sh 'mvn clean package'
    }
    
    stage('deploy to tomcat'){
        deploy adapters: [tomcat9(credentialsId: 'tomcat-creds', path: '', url: 'http://3.110.165.241:8081/')], contextPath: 'addressbook1', war: '**/*.war'
    }
}
