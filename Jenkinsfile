pipeline{
    agent{
        node{
            label "Linux-Node"
        }
    }
    tools{
        maven "Maven"
        jdk "jdk"
    }
    stages{
        stage("Commit"){
            steps{
                git 'https://github.com/Chetanrajput161194/Jenkins_Pipeline.git'
            }
            

        }
        stage("Build"){
            steps{
                sh 'mvn package'
            }
  
        }
        stage("Post-Build"){
            steps{
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }

        }
    }
}
