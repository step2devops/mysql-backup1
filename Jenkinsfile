def project_owner_team_email = 'jsnrahul@gmail.com'
pipeline{
    agent{
        label "server1"
    }
    parameters {        
        string(name: 'project_owner_team_email', defaultValue: project_owner_team_email, description: 'project_owner_team_email')

    }
    stages{
        stage('send-notification')
        {
            steps
            {
                script
                {
                    emailext subject: '${JOB_NAME}' - '${BUILD_NUMBER}', body: 'Job URL: ${BUILD_URL}', to: '${project_owner_team_email}'
                }
            }
        }
        stage("stage1"){
            steps{
                sh '''
                
                aws s3 cp /root/mysqlbackup.sql s3://backup-dbmysql/mysqlbackup"`date`".sql
                '''
            }
        }
    
        
    }

}