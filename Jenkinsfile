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
                    sh 'cd build &&./jinkens_c++'
                    archiveArtifacts artifacts: 'build/jinkens_c++', fingerprint: true
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
    post{
        always{
            sh 'pwd && ls'
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
