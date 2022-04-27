Codecov Setup
-   Register: https://about.codecov.io/
-   Add Repository
-   Retrieve token
-   Add secret CODECOV_TOKEN <-- token

Release Setup
-   Add <license>, <distributionManagement> in pom.xml
-   Add <developers>, <organization>,... in pom.xml (Optional)
-   Add .settings.xml
-   Use git tag (change pattern in `release.yml` if needed)

Unit test setup
-   Use jacoco
-   Add build plugin
    `<build>
        <plugins>
            <plugin>
                <groupId>org.jacoco</groupId>
                <artifactId>jacoco-maven-plugin</artifactId>
                <version>0.8.7</version>
                <executions>
                    <execution>
                        <id>default-prepare-agent</id>
                        <goals>
                        <goal>prepare-agent</goal>
                        </goals>
                    </execution>
                    <execution>
                        <id>report</id>
                        <phase>test</phase>
                        <goals>
                            <goal>report</goal>
                        </goals>
                    </execution>
                </executions>
                <configuration>
                <systemPropertyVariables>
                    <jacoco-agent.destfile>target/jacoco.exec</jacoco-agent.destfile>
                </systemPropertyVariables>
                <excludes>
                    <exclude>**/codecentric/sample/store/model/*</exclude>
                    <exclude>**/codecentric/sample/*.java</exclude>
                </excludes>
            </configuration>
            </plugin>
        </plugins>
    </build>`

Sonar Setup
-   Register: https://sonarcloud.io/sessions/init/github
-   Add Repository
-   Create token: https://sonarcloud.io/account/security
-   Add secret SONAR_TOKEN <-- token
-   Get Project Key, Organization Key: https://sonarcloud.io/project/information?id=...
-   Add secret SONAR_PROJECT_KEY <-- Project key
-   Add secret SONAR_ORGANIZATION <-- Organization
-   Add entry in <properties> in pom.xml
    `<properties>
        <sonar.organization>${env.SONAR_ORGANIZATION}</sonar.organization>
    </properties>`
-   Add secret SONAR_HOST_URL <-- https://sonarcloud.io