pipeline{
node any
stages{
stage('git checkout'){
steps{
scm checkout
}
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
sh 'mvn clean verify sonar:sonar
-Dsonar.projectName=PRADHAN
-Dsonar.projectKey=PRADHAN
-Dsonar.projectVersion=$BUILD_NUMBER'
}
}

}
}
