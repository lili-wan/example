/* Requires the Docker Pipeline plugin */
pipeline {
    agent any
    stages {
//         stage('Sequential') {
//             environment {
//                 FOR_SEQUENTIAL = "some-value"
//             }
        stages {
            stage('BUILD') {
                steps {
                    echo "BUILD"
                }
            }
            stage('Preprod') {
                parallel {
                    stages('qal-usw2-air') {
                        stage('test') {
                            steps {
                                echo "test"
                            }
                        }
                        stage('deploy') {
                            steps {
                                echo "deploy"
                            }
                        }
                    }
                    stages('e2e-usw2-air') {
                        stage('test') {
                            steps {
                                echo "test"
                            }
                        }
                        stage('deploy') {
                            steps {
                                echo "deploy"
                            }
                        }
                    }
                }
            }
            stage('Goto-Stage-Approval') {
                steps {
                    echo "approval"
                }
            }
            stage('Prod') {
                parallel {
                    stages('stg-usw2-air') {
                        stage('test') {
                            steps {
                                echo "test"
                            }
                        }
                        stage('deploy') {
                            steps {
                                echo "deploy"
                            }
                        }
                    }
                    stages('prd-usw2-air') {
                        stage('Go live in Prod approval') {
                            steps {
                                echo "approval"
                            }
                        }
                        stage('test') {
                            steps {
                                echo "test"
                            }
                        }
                        stage('create CR') {
                            steps {
                                echo "test"
                            }
                        }
                        stage('deploy') {
                            steps {
                                echo "deploy"
                            }
                        }
                        stage('Close CR') {
                            steps {
                                echo "test"
                            }
                        }
                    }
                }
            }
            //}
        }
    }
}
