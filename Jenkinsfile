#!groovy



node() {

    stage('Checkout')
    git branch: 'master', credentialsId: 'a43ef5e1-cb87-4045-b782-70c4db818374', url: 'https://github.com/mvvpavan/example.git'
    



    stage('Build')



    #def mvnHome = tool 'Maven 3.3.x'

    #env.JAVA_HOME = tool 'JDK 1.8'



    if (isUnix()) {

        sh "mvn -version"


    } else {

        bat "${mvnHome}\\bin\\mvn -version"

        bat "${mvnHome}\\bin\\mvn -Prun-its clean verify"

    }



    stage('Local installation')

    if (isUnix()) {

        sh "mvn clean install"

    } else {

        bat "${mvnHome}\\bin\\mvn -DskipTests install"

    }

}
