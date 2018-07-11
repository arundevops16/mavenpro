Maven:

Apache Maven is a software project management and comprehension tool. Based on the concept of a project object model (POM), Maven can manage a project&#39;s build, reporting and documentation from a central piece of information.

POM:

\* POM stands for Project Object Model. It is an XML representation of a Maven project held in a file named pom.xml.

\* The POM contains all necessary information about a project, as well as configurations of plugins to be used during the build process.

groupId:

\*This is generally unique amongst an organization or a project. All core Maven artifacts do live under the groupId. Group ID&#39;s do not necessarily use the dot notation.

artifactId:

\*The artifactId is generally the name that the project is known by.

version:

If code changes, those changes should be versioned, and this element keeps those versions in line.

Type- Packaging:

POM with groupId:artifactId:version: with default package above will be packaged as a jar. We could make it into a war by declaring a different packaging:

example: &lt;packaging&gt;war&lt;/packaging&gt;

POM:

\* POM stands for &quot;Project Object Model&quot;. It is an XML representation of a Maven project held in a file named pom.xml.

\* The POM contains all necessary information about a project, as well as configurations of plugins to be used during the build process.

\* Maven also handles project relationships that includes dependencies, and aggregation.

Dependencies:

\* The base of the POM is its dependency list. Most every project depends upon others to build and run correctly.

\* Maven downloads and links the dependencies during compilation and other goals that require them.

Maven life cycles:

Maven has 3 life cycles:

1. mvn clean

2. mvn default

3. mvn site

\* mvn default has some goals or phases:

# mvn validate:

will validate the project is correct and all necessary information is available

# mvn compile:

compile the source code of the project i.e., converts the java files into class files

# mvn test:

test the compiled source code using a suitable unit testing framework

# mvn package:

to make the compiled code into distributable format such as JAR or WAR

# mvn verify:

run any checks on results of integration tests to ensure quality criteria are met

# mvn install:

stores the package into our own local repository, to use in other projects locally

# mvn deploy:

deploys the final package to the remote repository for sharing with other developers and projects.



scope:

This element refers to the classpath of the task at hand as well as how to limit the transitivity of a dependency.

compile: This is the default scope, used if none is specified. Compile dependencies are available in all classpaths. Furthermore, those dependencies are propagated to dependent projects.

provided: This is much like compile, but indicates you expect the JDK or a container to provide it at runtime. It is only available on the compilation and test classpath, and is not transitive.

runtime - this scope indicates that the dependency is not required for compilation, but is for execution. It is in the runtime and test classpaths, but not the compile classpath.

test - this scope indicates that the dependency is not required for normal use of the application, and is only available for the test compilation and execution phases. It is not transitive.

system - this scope is similar to provided except that you have to provide the JAR which contains it explicitly. The artifact is always available and is not looked up in a repository.

systemPath:

It is used only if the the dependency scope is system. Otherwise, the build will fail if this element is set.



Maven Repositories:

Maven consists of mainly three repositories which contains all project jars, library jars and plugins can be stored and they can be used by maven in the project. They are:

1. Local

2. Central

3. Remote

Local repository:

\* Which resides in your machine and will be created when you run any maven command for the first time.

\* When you run a Maven build, then Maven automatically downloads all the dependency jars into the local repository.

\* It helps to avoid references to dependencies stored on remote machine every time a project is build.

\* Minimizes the time to download from the central

Central repository:

\* For security reasons organizations will not allow developers to connect browser every time they require a dependency for project. Before  starting of the project they download the required dependencies for the project and stores in central repository.

\* It contains a large number of commonly used libraries.

\* When Maven does not find any dependency in local repository, it starts searching in central repository.

Remote repository:

\* Incase Maven does not find a mentioned dependency in central repository as well then it stops the build process and throws the error. so we can use remote repository, which is developer&#39;s own custom repository containing required libraries or other project jars.
