pipeline{
agent any
stages{
stage('build'){
checkout scm
steps{
sh 'mvn clean package'
}
}
stage(' build and unit test'){
steps{
sh 'mvn clean verify -DskipITs=true';
junit '**/target/surefire-reports-TEST-*.xml'
archive 'target/*.jar'
}
}
stage('sonar test'){
steps{
sh 'mvn clean verify sonar:sonar -Dsonar.projectName=PRADHAN -Dsonar.projectKey=PRADHAN -Dsonar.projectVersion=$BUILD_NUMBER'
}
}

}
}
