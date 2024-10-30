pipeline{
    agent any
    tools{
        maven 'M2'
    }
    stages{
        stage("build my code"){
            steps{
            echo 'I am building my code in ${BRANCH_NAME}'
            }
        }
        stage("test my code"){
                    steps{
                    echo 'I am testing my code'
                    //sh 'mvn test -Dtest=orders.OrderTest'
                    bat 'mvn test -Dtest=orders.OrderTest'
                    bat 'isUnix()'
                    }
                }
    }

}