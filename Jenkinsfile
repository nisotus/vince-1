pipeline {
          agent any
                stages{
                        stage('one'){
                                steps{
                                        echo 'Hi, this is Vincent Oke'
                                }
                        }
                        stage('Two'){
                                steps{
                                        input ('Do you want to proceed?')
                                }
                        }
                        stage('Three'){
                                when{
                                        not {
                                                branch "master"
                                        }
                                }
                                
                                steps{
                                        echo "Hello"
                                }
                        }
                        stage('Four'){
                                parallel {
                                        stage('Unit Test'){
                                                        steps{
                                                                echo "Running the unit test..."                                        
                                                        }
                                        }
                                        stage('Integration Test'){
                                                        agent {
                                                                docker {
                                                                        reuseNode false
                                                                        image 'ubuntu'
                                                                }
                                                        }
                                                        steps{
                                                                echo "Running the integration test.."                                        
                                                        }
                                        }                                        
                                }
}
}                        
}
}
