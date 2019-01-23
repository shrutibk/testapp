pipeline{

    agent any

    stages {

        stage ('skip test'){

            steps {

                    sh 'mvn clean install -DskipTests'

                  }
        }
    stage ('install') {

            steps {

               
                    sh 'mvn test'
                    sh 'mvn install'


         
            }
        }


        stage ('Cucumber Reports') {

            steps {
                cucumber buildStatus: "UNSTABLE",
                    fileIncludePattern: "**/cucumber.json",
                    jsonReportDirectory: 'target'

            }

        }

    }
}

