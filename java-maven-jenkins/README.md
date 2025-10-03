# Hello Java Maven

A simple Java "Hello World" application built with Maven and Jenkins.

---

## Project Structure
```
hello-java-maven/
├── src/
│ └── main/
│ └── java/
│ └── HelloWorld.java
└── pom.xml
```

---

## Requirements
- Java 11+ (Java 8 compatible)
- Apache Maven 3.6+

---

## Build Locally
### Clean and package the project
```
mvn clean package
```

### Run the jar
java -cp target/hello-1.0.jar HelloWorld

### Expected output:
```
Hello, Jenkins + Maven!
```

---

# Jenkins Setup
```
Install Jenkins on EC2 (or local).

Configure JDK and Maven in Manage Jenkins → Global Tool Configuration.

Create a new Freestyle Job:

Workspace: hello-java-maven

Build → Invoke top-level Maven targets

Goals: clean package

Build the job.

Check console output for BUILD SUCCESS.
```

## Deliverables
```
Source code (HelloWorld.java, pom.xml)

Successful Jenkins build log

Packaged jar file in target/
```
