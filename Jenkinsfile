/* Requires the Docker Pipeline plugin */
pipeline {
    agent any
    stages {
        stage('BUILD') {
            steps {
                echo "BUILD"
            }
        }
        stage('Deploy') {
            parallel {
                stage('AIR') {
                    stages {
                        stage('get app image') {
                            when {
                                allOf {
                                    branch 'master'
                                }
                            }
                            steps {
                                echo 'get app image'
                            }
                        }
                        stage('qal-usw2-air') {
                            when {
                                allOf {
                                    branch 'master'
                                }
                            }
                            stages {
                                stage('Deploy') {
                                    steps {
                                        bat 'failed.bat'
                                    }
                                }
                            }
                        }
                        stage('e2e-usw2-air') {
                            when {
                                allOf {
                                    branch 'master'
                                }
                            }
                            stages {
                                stage('Deploy') {
                                    steps {
                                        echo 'deploy to e2e-usw2-air'
                                    }
                                }
                            }
                        }
                        stage('stg-usw2-air') {
                            when {
                                allOf {
                                    branch 'master'
                                }
                            }
                            stages {
                                stage('Deploy') {
                                    steps {
                                        echo 'deploy to stg-usw2-air'
                                    }
                                }
                            }
                        }
                        stage('prd-usw2-air') {
                            when {
                                allOf {
                                    branch 'master'
                                }
                            }
                            stages {
                                stage('Deploy') {
                                    steps {
                                        echo 'deploy to stg-usw2-air'
                                    }
                                 }
                            }
                        }
                    }
                }
                stage('CUSTOM') {
                    stages {
                        stage('get app image') {
                            when {
                                allOf {
                                    branch 'master'
                                }
                            }
                            steps {
                                echo 'get app image'
                            }
                        }
                        stage('qal-usw2-air') {
                            when {
                                allOf {
                                    branch 'master'
                                }
                            }
                            stages {
                                stage('Deploy') {
                                    steps {
                                        echo 'deploy to qal-usw2-air'
                                    }
                                }
                            }
                        }
                        stage('e2e-usw2-air') {
                            when {
                                allOf {
                                    branch 'master'
                                }
                            }
                            stages {
                                stage('Deploy') {
                                    steps {
                                        echo 'deploy to e2e-usw2-air'
                                    }
                                }
                            }
                        }
                        stage('stg-usw2-air') {
                            when {
                                allOf {
                                    branch 'master'
                                }
                            }
                            stages {
                                stage('Deploy') {
                                    steps {
                                        echo 'deploy to stg-usw2-air'
                                    }
                                }
                            }
                        }
                        stage('prd-usw2-air') {
                            when {
                                allOf {
                                    branch 'master'
                                }
                            }
                            stages {
                                stage('Deploy') {
                                    steps {
                                        echo 'deploy to stg-usw2-air'
                                    }
                                 }
                            }
                        }
//                         stage('BUILD:') {
//                             when {
//                                 anyOf {
//                                     branch 'master'
//                                 }
//                             }
//                             stages {
//                                 stage('Get Next Release Version') {
//                                     steps {
//                                         echo 'Get Next Release Version'
//                                     }
//                                 }
//                                 stage('Build App') {
//                                     parallel {
//                                         stage('Docker Multi Stage Build') {
//                                             steps {
//                                                 echo 'Docker Multi Stage Build'
//                                             }
//                                         }
//                                         stage('API:') {
//                                             stages {
//                                                 stage('Linting') {
//                                                     steps {
//                                                         echo 'Linting'
//                                                     }
//                                                 }
//                                                 stage('Merge and Flatten Spec') {
//                                                     steps {
//                                                         echo 'Merge and Flatten Spec'
//                                                     }
//                                                 }
//                                             }
//                                         }
//                                     }
//                                 }
//                             }
//                         }
                    }
                }
            }
        }
    }
}
