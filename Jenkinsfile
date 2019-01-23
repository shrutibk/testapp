pipeline{

    agent any

    stages {

        stage ('Clean') {

            steps {

                    sh 'mvn clean'

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
