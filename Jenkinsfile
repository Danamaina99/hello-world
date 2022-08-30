def call(Map pipelineParams) {
  
  mavenTool = "Maven 3";
  
  def buildAndUploadSnapshot
  def nextSnapshotVersion
  
  pipeline {
    agent {
      label "linux"
    }
    
    tools {
       maven "${mavenTool}"
    }
    
    /*parameteres {
      string(defaultValue: 'NA',  description: 'Next Snapshot Version (-SNAPSHOT will be added automatically)', name: 'NEXT_SNAPSHOT_VERSION', trim:true)
      booleanParam(name: 'BUILD_AND_UPLOAD_SNAPSHOT', defaultValue: false, description: 'Do you want to build this branch and upload to SNAPSHOTS? (default of true for master branch, false for others)')
    } **/

    stages {
      stage ('Build setup') {
        steps {
          script {
            buildBranch = getBranchName(branch: "${BRANCH_NAME}");
            buildAndUploadSnapshot = params.BUILD_AND_UPLOAD_SNAPSHOT == true || buildBranch == 'master'
            nextSnapshotVersion = params.NEXT_SNAPSHOT_VERSION + "-SNAPSHOT"
          }
        }
      }
    }
  }

  
          
  
      
        
  
