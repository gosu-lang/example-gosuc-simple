# example-gosuc-simple
Example usage of the Gosu compiler component for Maven's compiler plugin

## Assumptions
This project assumes a 'pure' Gosu project with only Gosu-based classes (i.e. no Java).

## POM configuration
There are three notable tweaks to the build section of the Maven POM:
  1. Set source and test roots
  2. Set the `compilerID` property of the `maven-compiler-plugin` to `gosuc`
  3. Tell `maven-compiler-plugin` to depend on the `plexus-compiler-gosu` artifact

## Usage/Outcome
Executing `$ mvn test` should produce the following output:
```
[INFO] --- maven-compiler-plugin:3.3:compile (default-compile) @ example-gosuc-simple ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 2 source files to /home/kmoore/dev/gosu-lang/example-gosuc-simple/target/classes
[INFO] Adding Gosu JARs to compiler classpath
...
[INFO] --- maven-compiler-plugin:3.3:testCompile (default-testCompile) @ example-gosuc-simple ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 1 source file to /home/kmoore/dev/gosu-lang/example-gosuc-simple/target/test-classes
[INFO] Adding Gosu JARs to compiler classpath
...
-------------------------------------------------------
 T E S T S
-------------------------------------------------------
Running example.FooTest
newing a Foo
Hello, got the argument 'eureka'
Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.698 sec

Results :

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
```