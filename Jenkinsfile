pipeline{
    agent any
    stages{
        stage("A"){
            steps{
                echo "========executing A========"
                sh 'mkdir build && cd build && cmake .. && make'
            }
            post{
                always{
                    echo "========always========"
                    cleanup()
                }
                success{
                    echo "========A executed successfully========"
                    sh 'ls && cd build && ./jinkens_c++'
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
