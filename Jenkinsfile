pipeline{
    agent{
        lable 'server1'
    }
    stages{
        stage('stage1'){
            steps{
                sh '''
                d=date
                aws s3 cp /root/mysqlbackup.sql s3://backup-dbmysql/mysqlbackup"$d".sql
                '''
            }
        }
    }
}