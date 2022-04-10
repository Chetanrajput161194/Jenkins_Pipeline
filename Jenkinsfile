pipeline{
    agent{
        node{
            label "maven"
        }
    }
    tools{
        maven "M2_HOME"
    }
    stages{
        stage("Commit"){
            when{
            buildingTag()
            }
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
