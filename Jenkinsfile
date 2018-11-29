pipeline {
    agent none
    stages {
        stage('Flash Bootloader') {
          agent any
          steps {
               echo "Flash the bootloader"
          }
        }
        stage('Download Package') {
            agent any
            steps {
                echo "Stage to Download the package"
            }
        }
       stage('Flash Package') {
            agent any
            steps {
                echo "Stage to flash the package"
            }
        }
       stage('Enable ADB') {
            agent any
            steps {
                echo "Stage to enable the ADB"
            }
        }
       stage('Initial Settings') {
            agent any
            steps {
                echo "Stage to perform initial settings"
            }
        }
       stage('Home Screen Capture') {
            agent any
            steps {
                echo "Stage to perform home screen capture"
            }
        }
       stages('Run Test'){
            steps {
                parallel{
                    stage("Run CTS Test") {
                        agent {
                            docker {image 'ubuntu'}
                        }
                    steps{
                           echo "Run the CTS Test here...."
                        }
                    }
                    stage("Run GTS Test") {
                        agent {
                            docker {image 'ubuntu'}
                        }
                    steps {
                          echo "Run the GTS Test here...."
                        }   
                    }
                }
            }
        }
       stage('Grab & Upload Results'){
            agent any
            steps {
                echo "Stage to Grab & Upload Results"
            }
        }
    }
}
