pipeline {
    agent any 
    tools {
         maven 'maven'
         jdk 'java'
    }
    stages {

        stage('Stage-0 : Clean') { 
            steps {
                sh 'mvn clean'
            }
        }
         stage('Stage-1 : Validate') { 
            steps {
                sh 'mvn validate'
            }
        }
         stage('Stage-2 : Compile') { 
            steps {
                sh 'mvn compile'
            }
        }
         stage('Stage-3 : Test') { 
            steps {
                sh 'mvn test -DskipTests'
            }
        }
          stage('Stage-4 : Install') { 
            steps {
                sh 'mvn install -DskipTests'
            }
        }
          stage('Stage-5 : Verify') { 
            steps {
                sh 'mvn verify -DskipTests'
            }
        }
          stage('Stage-6 : Package') { 
            steps {
                sh 'mvn package -DskipTests'
            }
        }

//            stage('Stage-7 : Deploy an Artifact to Artifactory Manager i.e. Nexus/Jfrog') { 
//             steps {
//                 sh 'mvn deploy -DskipTests'
//             }
//         }

          stage('Stage-7 : Deployment - Deploy a Artifact devops-3.0.0-SNAPSHOT.war file to Tomcat Server') { 
            steps {
                sh 'curl -u chethan:Chethan@22 -T target/**.war "http://172.173.179.196:8080/manager/text/deploy?path=/mahesh&update=true"'
            }
        } 
  
          stage('Stage-8 : SmokeTest') { 
            steps {
                sh 'curl --retry-delay 10 --retry 5 "http://172.173.179.196:8080/mahesh"'
            }
        }

  
    }
}








// pipeline {
//     agent any 
//     tools {
//          maven 'maven'
//          java 'java'
//     }
//     stages {

//         stage('Stage-1 : Clean') { 
//             steps {
//                 sh 'mvn clean'
//             }
//         }
//          stage('Stage-2 : Validate') { 
//             steps {
//                 sh 'mvn validate'
//             }
//         }
//          stage('Stage-3 : Compile') { 
//             steps {
//                 sh 'mvn compile'
//             }
//         }
//          stage('Stage-4 : Test') { 
//             steps {
//                 sh 'mvn test'
//             }
//         }
//           stage('Stage-5 : Install') { 
//             steps {
//                 sh 'mvn install'
//             }
//         }
//           stage('Stage-6 : Verify') { 
//             steps {
//                 sh 'mvn verify'
//             }
//         }
//           stage('Stage-7 : Package') { 
//             steps {
//                 sh 'mvn package'
//             }
//         }
//           stage('Stage-8 : Deployment - Deploy a Artifact devops-3.0.0-SNAPSHOT.war file to Tomcat Server') { 
//             steps {
//                 sh 'curl -u chethan:Chethan@22 -T target/**.war "http://172.173.179.196:8080/manager/text/deploy?path=/maheshbabuu&update=true"'
//             }
//         } 
//           stage('Stage-9 : SmokeTest') { 
//             steps {
//                 sh 'curl --retry-delay 10 --retry 5 "http://172.173.179.196:8080/maheshbabuu"'
//             }
//         }
//     }
// }
