node {
    git url: 'https://github.com/varyvoltest/maven-basic-simple'
    def mvnHome = tool 'M3'
    cbEnv = ["PATH+MVN=${mvnHome}/bin", "MAVEN_HOME=${mvnHome}"]
    withEnv(cbEnv) {
        try {
            sh 'mvn test -DmavenBasicNotFail'
        } catch (any) {
            currentBuild.result = 'FAILURE'
            throw any
        }
    }
}