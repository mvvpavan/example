#!groovy



node() {
parameters {
        booleanParam(defaultValue: true, description: '', name: 'userFlag')
    }
    stage('Checkout')
    git credentialsId: 'a43ef5e1-cb87-4045-b782-70c4db818374', url: 'https://github.com/mvvpavan/example.git'
    



    stage('Build')



    def mvnHome = tool 'maven'

    env.JAVA_HOME = tool 'JDK'



    if (isUnix()) {
        echo "flag: ${params.userFlag}"
        sh "'${mvnHome}/bin/mvn' -version"
            


    } else {

        bat "${mvnHome}\\bin\\mvn -version"

        bat "${mvnHome}\\bin\\mvn -Prun-its clean verify"

    }



    stage('Local installation')

    if (isUnix()) {

        sh "'${mvnHome}/bin/mvn' clean install"

    } else {

        bat "${mvnHome}\\bin\\mvn -DskipTests install"

    }

}
