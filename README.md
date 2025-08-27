# Jenkins CI Practice (Java + Maven)

Simple app that prints **"A commit has been made"**.

## Run locally
```bash
mvn -q -DskipTests package
java -cp target/jenkins-ci-practice-1.0-SNAPSHOT.jar com.example.App
