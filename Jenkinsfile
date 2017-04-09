node("launchpad-maven") {

   stage "Checkout"
        checkout scm

   stage "Standalone Integration Tests"
        sh "mvn clean verify"

   stage "OpenShift Integration Tests"
        sh "mvn clean verify -Popenshift -Dskip.surefire.tests=true"

   stage "Deploy"
        sh "mvn fabric8:apply -Popenshift"
}
