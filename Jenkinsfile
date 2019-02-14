pipeline{
agent any
stages{
stage('build'){
sh 'mvn clean package'
}
stage(' build and unit test'){
sh 'mvn clean verify -DskipITs=true';
junit '**/target/surefire-reports-TEST-*.xml'
archive 'target/*.jar'
}
stage('sonar test'){
sh 'mvn clean verify sonar:sonar -Dsonar.projectName=PRADHAN -Dsonar.projectKey=PRADHAN -Dsonar.projectVersion=$BUILD_NUMBER'
}

}
}
