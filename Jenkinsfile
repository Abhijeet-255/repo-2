pipeline {
             agent {
                      label {
                                    label "built-in"
                                    customWorkspace "/mnt/abhi"
                      }
             }
             
             environment {
                                    url = "https://github.com/Abhijeet-255/project-RDS.git"
             }

             stages {
                         stage("CLONE_PROJECT") {
                                             steps {
                                                      sh "rm -rf *"
                                                      sh "git clone $url"
                                             }
                          }
                           

                         stage("BUILD_PROJECT") {
                                             steps {
                
                                                     sh "cd project-RDS && mvn clean install -DskipTest=true"
                                             }
                         }

                         stage("COPY") {
                                              steps{
                                                    sh "rm -rf /mnt/wars/*"
                                                    sh "cp -r project-RDS/target/LoginWebApp /mnt/wars"
                                              }

                         }
              }
}
                                                           
