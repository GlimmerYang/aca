## Android Code Quality

This project integrates a combination of code analysis tools. Use for iBOXPAY android projects. fork from https://github.com/ribot/android-boilerplate/tree/master/config/quality

### Code Analysis tools

The following code analysis tools are set up on this project:

* [PMD](https://pmd.github.io/): It finds common programming flaws like unused variables, empty catch blocks, unnecessary object creation, and so forth. See [this project's PMD ruleset](config/quality/pmd/pmd-ruleset.xml).

```
./gradlew pmd
```

* [Findbugs](http://findbugs.sourceforge.net/): This tool uses static analysis to find bugs in Java code. Unlike PMD, it uses compiled Java bytecode instead of source code.

```
./gradlew findbugs
```

* [Checkstyle](http://checkstyle.sourceforge.net/): It ensures that the code style follows [our Android code guidelines](https://github.com/ribot/android-guidelines/blob/master/project_and_code_guidelines.md#2-code-guidelines). See our [checkstyle config file](config/quality/checkstyle/checkstyle-config.xml).

```
./gradlew checkstyle
```

### The check task

To ensure that your code is valid and stable use check:

```
./gradlew check
```

### How to use

Clone this project into your project `$PROJECT/config/qulity`
and modify `app/build.gradle`，add this line in the bollow：

```
apply from: '../config/quality/quality.gradle'
```

##### configure

when use this config first time in old project, it will complains tons of  errors when compile, so you can turn off the error.

modify `config/quality/quality.gradle`，set `ignoreFailures ` is `true`：

```
ignoreFailures = true
```

