# Execute Multi-Project Builds
 
__Category: Gradle__

Large projects in Gradle are typically split into smaller, inter-dependent modules. To display project structure, you can use the Gradle `projects` command.
 
```shell
gradle -q projects
```
 
To see a list of the tasks of a project, run gradle `:<project-path>:tasks`
 
For example, to list tasks for a submodule called `api`:
 
```shell
gradle :api:tasks
```
 
To build a submodule called `api`:
 
```shell
gradle :api:build
```
 
See [Executing Multi-Project Builds](https://docs.gradle.org/current/userguide/intro_multi_project_builds.html) for more details.
