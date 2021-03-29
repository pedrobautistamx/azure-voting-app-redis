pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            powershell(script: 'Write-Output "Hello W"')
         }
      }
      stage('Docker Build') {
         steps {
            powershell(script: 'docker images -a')
            powershell(script: """
               cd azure-vote/
               docker images -a
               docker build -t jenkins-pipeline .
               docker images -a
               cd ..
            """)
         }
      }
   }
}