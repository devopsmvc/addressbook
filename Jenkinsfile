node{
    stage('code checkout'){
        echo 'checking out the code'
        git 'https://github.com/devopsmvc/addressbook.git'
    }

    stage('Compile'){
        echo 'Compling Code'
        sh 'mvn complie'
    }

    stage('Testing the Code'){
        echo 'Testing the Code'
        sh 'mvn test'
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
        deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://13.234.17.224:8081/')], contextPath: 'addressbook', war: '**/*.war'
    }

}
