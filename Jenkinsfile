        pipeline {
            agent {
              node {
                label 'nodejs'
              }
            }
            options {
                timeout(time: 20, unit: 'MINUTES')
            }
            stages {                                
                stage('build') {
                    steps {
                      sh 'make build'
                      sh 'npm install grunt -g'
                      sh 'grunt test'
                      sh 'hack/verify-dist.sh'
                    } // steps
                } // stage
            } // stages
        } // pipeline
