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
                }
                success{
                    echo "========A executed successfully========"
                    sh './jinkens_c++'
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
    post{
        always{
            sh 'pwd'
            echo "========always========"
            deleteDir()
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
