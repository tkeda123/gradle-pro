https://medium.com/@simionrazvan/how-to-create-a-gradle-library-and-publish-it-on-nexus-34be19b520aa
https://docs.gradle.org/current/userguide/publishing_maven.html#sec:identity_values_in_the_generated_pom
https://github.com/opendevstack/ods-quickstarters/issues/785

publishing {
publications {
maven(MavenPublication) {
from components.java
groupId = 'tatsuya.gradle'
artifactId = 'library'
version = '1.1'
}
}
repositories {
maven {
// Nexus の URL を指定
url = 'http://localhost:8081/repository/maven-releases/'
// Nexus への認証情報を設定
credentials {
username = 'admin'
password = 'password'
}
allowInsecureProtocol = true
}
}
