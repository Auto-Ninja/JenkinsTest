pipeline{
    agent any
    tools{
        maven 'M2'
    }
    environment
    {
        MY_VERSION = 'DEV_VERSION'
    }
    parameters
        {
            choice(name: 'VERSION',choices: ['1.2.1','1.2.2','2.1.0'])
            booleanParam(name: 'executeTests',defaultValue:true,description:'Decide to execute test in the build')
            choice(name: 'PLATFORM_FILTER', choices: ['all', 'linux', 'windows', 'mac'], description: 'Run on specific platform')
        }
    stages{
        stage("build my code"){
            steps{
            echo "I am building my code from ${BRANCH_NAME} & ${MY_VERSION} -- ${params.VERSION}"
            }
        }
        stage("test my code")
        {
            when{
                    expression{
                        params.executeTests
                    }
                }
                steps{
                    echo 'I am testing my code'
                    //sh 'mvn test -Dtest=orders.OrderTest'
                    bat 'mvn test -Dtest=orders.OrderTest'
                    }
        }
    }
    post {
                    always {
                        allure includeProperties:
                         false,
                         jdk: '',
                         results: [[path: 'build/allure-results']]
                    }
                }

}