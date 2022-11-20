node{
    stage('code checkout'){
        git 'https://github.com/devopsmvc/addressbook.git'
    }
    
    stage('clean.. compile... test... package...'){
        sh 'mvn clean package'
    }
    
    stage('deploy to tomcat'){
        deploy adapters: [tomcat9(credentialsId: 'tomcat-creds', path: '', url: 'http://43.204.212.207:8081/')], contextPath: 'addressbook', war: '**/*.war'
    }
}
