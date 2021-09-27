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
            git 'https://github.com/Chetanrajput161194/Jenkins_Pipeline.git'

        }
        stage("Build"){
            sh 'mvn package'
  
        }
        stage{"Post-Build"}{
            archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false

        }
    }
}
