#!groovy​
@Library('sprockets@2.9.8') _

//Note: Just builds the jar and pushes it to nexus.
node () {

    def g = new gradlew()
    def c = new common()

    stage('checkout') {
        checkout scm
    }

    stage('build') {
        c.exportProperties(g)
        sh './gradlew jar'
    }

    stage('publish') {
        sh './gradlew publish'
    }
}
