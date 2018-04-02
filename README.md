# Android Maven BOM test

In this repository, I would like to try the Gradle's [improved pom support](https://docs.gradle.org/4.6/release-notes.html#bom-import).

I want to resolve version of `gson` from Spring Boot BOM

```groovy
dependencies {
    // import a BOM
    implementation 'org.springframework.boot:spring-boot-dependencies:1.5.8.RELEASE'
    // define dependencies without versions
    implementation 'com.google.code.gson:gson'
}
```

Run this command to check `gson`'s version:
```
./gradlew :android-maven-bom-test:dependencies --configuration releaseCompileClasspath
```

Version of `gson` is provided by Spring Boot BOM:
```
releaseCompileClasspath - Resolved configuration for compilation for variant: release
+--- org.springframework.boot:spring-boot-dependencies:1.5.8.RELEASE
|    \--- com.google.code.gson:gson:2.8.2
\--- com.google.code.gson:gson -> 2.8.2
```