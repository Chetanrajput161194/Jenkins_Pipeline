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
        stage("Build"){
            when{
            buildingTag()
            }
            steps{
                sh 'mvn package'
                sh 'cp target/*.jar /home/ubuntu/ && java -jar *.jar'
            }
  
        }
        stage("Post-Build"){
            steps{
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }

        }
    }
}
