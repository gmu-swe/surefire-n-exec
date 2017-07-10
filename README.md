#surefire-n-exec

JUnit4 provider for Maven Surefire that will rerun all tests a specified number of times.

To use it (after installing), add it as a dependency to the surefire plugin (NOT a dependency of your entire build! Just for surefire), and configure the number of times to rerun each test (total runs = 1 + reruns).

Example:

```
<build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-surefire-plugin</artifactId>
                <version>2.19.1</version>
                <dependencies>
                    <dependency>
                        <artifactId>surefire-n-exec</artifactId>
                        <groupId>edu.gmu.swe.surefire</groupId>
                        <version>2.19.1</version>
                    </dependency>
                </dependencies>
                <configuration>
                    <forkMode>once</forkMode>
                    <properties>
                        <property>
                            <name>rerunAllTests</name>
                            <value>100</value>
                        </property>
                    </properties>
                </configuration>
            </plugin>
        </plugins>
</build>
```
