# Maven Projects

This repository contains two simple Maven projects:

1. **first-app**: A basic Maven app.
2. **calculator-executable-jar**: An application that can be built into an executable JAR.

## Building and Running

You can build both projects using Maven:

```bash
cd first-app
mvn clean install

cd ../calculator-executable-jar
mvn clean package
```

To run the calculator executable JAR:
```bash
java -jar calculator-executable-jar/target/calculator-executable-jar-1.0-SNAPSHOT.jar
```
