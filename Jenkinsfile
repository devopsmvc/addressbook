node("slave")
{
    stage('code checkout'){
        echo 'checking out the code'
        git 'https://github.com/devopsmvc/addressbook.git'
    }

    stage('Compile'){
        echo 'Compling Code'
        sh 'mvn compile'
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
        deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://13.127.190.20:8081/')], contextPath: 'addressbook-pipeline', war: '**/*.war'
    }

}
