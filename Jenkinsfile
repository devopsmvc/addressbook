node{
    stage('code checkout'){
        echo 'checking out the code'
        git 'https://github.com/devopsmvc/addressbook.git'
    }

    stage('workspace stage'){
        echo 'cleaning the workspace'
        sh 'mvn clean'
    }

    stage('complie, test, package'){
        echo 'Compiling, testing and packaging source code'
        sh 'mvn package'
    }

    stage('deploy'){
        echo 'deploy the address book to tomcat9'
        deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.110.102.147:8081/')], contextPath: 'addressbook', war: '**/*.war'
    }

}
