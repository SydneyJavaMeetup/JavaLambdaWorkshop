# Java Lambda Workshop
Notes and examples for the Sydney Java Meetup's Lambda Workshop

## Workshop Outline

### Prerequisites
* Java SE JDK 8 (https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
* IntelliJ / Eclipse (https://www.jetbrains.com/idea/download)
  * workshop demos done in IntelliJ
* SAM CLI (https://github.com/awslabs/aws-sam-cli/blob/develop/docs/installation.rst)
  * requires Python and Docker
* (Optional) An AWS account to deploy your code to the cloud!
* Enthusiasm!

## PART 1
### Project Instantiation
* Initialize SAM CLI Java project
    ```
    sam init -r java8 -n starry-skies
    ```
* Run
    ```bash
    cd starry-skies
    mvn clean test    
    ```
* Open in IntelliJ for some IDE goodness
```bash
    idea .
```
* Remember to fix the module Java versions if IntelliJ didn't pick them up
* Build the package
```
    mvn package
```
At this point we should have an uber-jar in starry-skies/target/HelloWorld-1.0.jar.

### Running locally
* Run the service:
    ```bash
    sam local start-api
    ```
* Start a browser:
    [http://127.0.0.1:3000/hello](http://127.0.0.1:3000/hello)

### Debugging it locally
* Add a 'remote' debug configuration in IntelliJ / equivalent Eclipse
* Put a breakpoint in App::handler
* Run the service:
    ```bash
    sam local start-api -d 9292
    ```
* Start a browser:

    [http://127.0.0.1:3000/hello](http://127.0.0.1:3000/hello)
    
    (the local lambda will pause waiting for you to attach a debugger)
    
    
# BREAK
Take a break for questions and getting everyone up to the same place.

## PART 2
### A Little Style
Let's upgrade the default SAM CLI implementation with some generics and stronger typing.

### Functionality
Let's make our function do something fun!

# BREAK
## PART 3
### Cloud Deployment
Let's deploy our functions to AWS cloud and invoke them from the browser.
### Cloud Monitoring
Let's add some metrics to our function and show them on a dashboard.
