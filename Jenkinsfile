pipeline{
    agent any
    stages{
        stage ('checkout the code from SCM'){
            steps{
                echo 'checkout the code'
            }
        }
        stage ('Build the project'){
            steps{
                echo 'building the project'
                sh 'mvn clean install -DskipTests'
            }
        }
        stage('Sonarqube'){
            steps{
                echo 'Sonar Codequality'
                sh '''
                mvn clean verify sonar:sonar \
            -Dsonar.projectKey=Mobile-Store \
            -Dsonar.host.url=http://20.150.195.193:9000 \
            -Dsonar.login=sqp_810d3fc82b7ccce7f99d9273347883e663b637cd
                    '''
            }
        } 
    }
}