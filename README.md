# MCOMPILER-342

<https://issues.apache.org/jira/browse/MCOMPILER-342>

Compile with JDK 10, it works:

```
$ mvn clean compile
```

Compile with JDK 11, it doesn't work anymore:

```
$ mvn clean compile -Dmaven.compiler.source=11 -Dmaven.compiler.target=11
...
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary:
[INFO]
[INFO] Java Examples - Java 9 ............................. SUCCESS [  0.181 s]
[INFO] Java Examples - Java 9 Dev API ..................... SUCCESS [  0.814 s]
[INFO] Java Examples - Java 9 Dev Core .................... FAILURE [  0.028 s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 1.115 s
[INFO] Finished at: 2018-05-15T09:23:11+02:00
[INFO] Final Memory: 11M/3072M
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.7.0:compile (default-compile) on project java-examples-dev-core: Execution default-compile of goal org.apache.maven.plugins:maven-compiler-plugin:3.7.0:compile failed: Unsupported class file major version 55 -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/PluginExecutionException
[ERROR]
[ERROR] After correcting the problems, you can resume the build with the command
[ERROR]   mvn <goals> -rf :java-examples-dev-core
```

