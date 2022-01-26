IntelliJ IDEA 2021.3.1 (Community Edition)
Build #IC-213.6461.79, built on December 28, 2021
Runtime version: 11.0.13+7-b1751.21 amd64
VM: OpenJDK 64-Bit Server VM by JetBrains s.r.o.
Windows 10 10.0
GC: G1 Young Generation, G1 Old Generation
Memory: 998M
Cores: 8
Non-Bundled Plugins:
Docker (213.6461.58)

Kotlin: 213-1.5.10-release-949-IJ6461.79

setup docker:

In CMD:
Go to project path

./gradlew build
java -jar build\libs\springboot-basic-0.0.1-SNAPSHOT.jar

C:\Users\devar\Intellij_Workspace\springboot-basic>docker build -t springio/gs-spring-boot-docker .
[+] Building 1.7s (8/8) FINISHED
=> [internal] load build definition from Dockerfile                                                                                                                                                          0.0s
=> => transferring dockerfile: 239B                                                                                                                                                                          0.0s
=> [internal] load .dockerignore                                                                                                                                                                             0.0s
=> => transferring context: 2B                                                                                                                                                                               0.0s
=> [internal] load metadata for docker.io/library/openjdk:8-jdk-alpine                                                                                                                                       1.3s
=> [internal] load build context                                                                                                                                                                             0.1s
=> => transferring context: 17.56MB                                                                                                                                                                          0.1s
=> [1/3] FROM docker.io/library/openjdk:8-jdk-alpine@sha256:94792824df2df33402f201713f932b58cb9de94a0cd524164a0f2283343547b3                                                                                 0.0s
=> CACHED [2/3] RUN addgroup -S spring && adduser -S spring -G spring                                                                                                                                        0.0s
=> [3/3] COPY build/libs/springboot-basic-0.0.1-SNAPSHOT.jar app.jar                                                                                                                                         0.1s
=> exporting to image                                                                                                                                                                                        0.1s
=> => exporting layers                                                                                                                                                                                       0.1s
=> => writing image sha256:3ae6182c406520d78f8e7099fd0a8ea38deaabe010df4f1adf4e85ab63ea61c7                                                                                                                  0.0s
=> => naming to docker.io/springio/gs-spring-boot-docker                                                                                                                                           0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them

C:\Users\devar\Intellij_Workspace\springboot-basic>docker run -p 8080:8080 springio/gs-spring-boot-docker
<App Runs>


C:\Users\devar\Intellij_Workspace\springboot-basic>docker images
REPOSITORY                       TAG       IMAGE ID       CREATED          SIZE
springio/gs-spring-boot-docker   latest    3ae6182c4065   12 minutes ago   122MB
<none>                           <none>    7c5a0dffb970   17 minutes ago   105MB
<none>                           <none>    132ae11acb52   29 minutes ago   105MB
docker101tutorial                latest    8e791ee264da   8 days ago       28.8MB
devarajgr09/docker101tutorial    latest    8e791ee264da   8 days ago       28.8MB
alpine/git                       latest    c6b70534b534   2 months ago     27.4MB
----------------------------------------------------
Build a Docker Image with Gradle
You can build a tagged docker image with Gradle in one command:

./gradlew bootBuildImage --imageName=springio/gs-spring-boot-docker

C:\Users\devar>docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

TO STOP:

docker stop goofy_brown
81c723d22865


If you like, you can also delete the container (it is persisted in your filesystem somewhere under /var/lib/docker) when you are finished with it:

docker rm goofy_brown