pipeline{
agent any
stages{
stage('build'){
steps{
sh 'mvn clean package'
}
}
stage('sonar test'){
steps{
sh 'mvn clean verify sonar:sonar -Dsonar.projectName=PRADHAN -Dsonar.projectKey=PRADHAN -Dsonar.projectVersion=$BUILD_NUMBER'
}
}
}
}
