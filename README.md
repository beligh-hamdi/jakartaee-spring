# Jakarta EE for Spring Developers

Sample code for migrating to Spring 6 / Spring Boot 3




https://openliberty.io/blog/2021/03/17/eclipse-transformer.html

https://iwtyo.today/migrating-from-javax-to-jakarta


https://medium.com/@AlexanderObregon/how-to-migrate-from-java-ee-to-jakarta-ee-tips-and-best-practices-f19530c3bb1d

https://omnifish.ee/2023/05/29/upgrading-to-jakarta-ee-10-transforming-applications-with-eclipse-transformer/

https://github.com/eclipse/transformer/issues/48
<!-- https://mvnrepository.com/artifact/org.tomitribe.transformer/org.eclipse.transformer -->
<dependency>
    <groupId>org.tomitribe.transformer</groupId>
    <artifactId>org.eclipse.transformer</artifactId>
    <version>0.1.1</version>
</dependency>


     <plugin>
        <groupId>org.tomitribe.transformer</groupId>
        <artifactId>transformer-maven-plugin</artifactId>
        <version>0.0.8</version>
        <configuration>
          <classifier>jakartaee9</classifier>
        </configuration>
        <executions>
          <execution>
            <goals>
              <goal>run</goal>
            </goals>
            <phase>package</phase>
          </execution>
        </executions>
      </plugin>

https://github.com/ivargrimstad/jakartaee-spring.git

https://speakerdeck.com/ivargrimstad/why-spring-matters-to-jakarta-ee-and-vice-versa-eba1b242-2d02-4021-8741-7feaa42beff1?slide=25

https://www.youtube.com/watch?v=9IfuxAP0920&list=PLe6FX2SlkJdQyqVIMrhYRYx-3KYDASifZ&index=13


mvn dependency:tree -Dincludes=jakarta.validation:jakarta.validation-api


java -jar transformer/org.eclipse.transformer.cli-0.5.0.jar dep-module/target/dep-module.jar

java -jar transformer/org.eclipse.transformer.cli-0.5.0.jar  boot-module/target/boot-module-0.0.1-SNAPSHOT.jar


java -jar duke-module/target/duke-module.jar


### 
duke-lib
mvn clean install

/Users/beligh/Desktop/jakartaee-spring/duke-lib/target/duke-lib.jar
/Users/beligh/.m2/repository/dukes/duke-lib/1.0/duke-lib-1.0.jar

1 - Download JAR from .m2 repository
2 - Copy it to the transformer folder
3 - Run transformer


cp /Users/beligh/.m2/repository/dukes/duke-lib/1.0/duke-lib-1.0.jar tmp

java -jar transformer/org.eclipse.transformer.cli-0.5.0.jar  tmp/duke-lib-1.0.jar


mvn install:install-file -Dfile=tmp/output_duke-lib-1.0.jar -DgroupId=dukes -DartifactId=duke-lib -Dversion=2.0 -Dpackaging=jar



https://github.com/OmniFish-EE/upgrading-jakarta-ee-applications/blob/main/javax-jakarta-transform-dependencies-uberjar/transform-dependencies/pom.xml