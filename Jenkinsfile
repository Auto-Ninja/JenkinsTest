pipeline{
    agent any
    tools{
        maven 'M2'
    }
    stages{
        stage("build my code"){
            steps{
            echo 'I am building my code'
            }
        }
        stage("test my code"){
                    steps{
                    echo 'I am testing my code'
                    sh 'mvn test -Dtest=orders.OrderTest'
                    }
                }
    }

}