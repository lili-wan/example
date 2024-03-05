/* Requires the Docker Pipeline plugin */
pipeline {
    agent any
    stages {
        stage('BUILD') {
            steps {
                echo "BUILD"
            }
        }
        stage('Preprod') {
            parallel {
                stage('qal-usw2-air') {
                    stages {
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
                stage('e2e-usw2-air') {
                    stages {
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
        }
        stage('Goto-Stage-Approval') {
            steps {
                echo "approval"
            }
        }
        stage('Prod') {
            parallel {
                stage('stg-usw2-air') {
                    stages {
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
                stage('prd-usw2-air') {
                    stages {
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
        }
    }
}
