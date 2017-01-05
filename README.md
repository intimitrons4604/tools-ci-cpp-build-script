# C++ Robot Project CI Build Tool
This repository contains a simple Gradle script that downloads WPILib and builds C++ robot code. It is intended to be used for CI builds.

## How to Use
Simply run `./gradlew build` from the directory containing `build.gradle`. You can also run `./gradlew clean`, to clean any intermediate outputs. Better still, use `./gradlew clean build` to clean and then build in one shot.

Both `clean` and `build` are tasks in Gradle terminology. There are many other available tasks, such as `components` or `dependencies`. Try running the `tasks` task or consult the Gradle documentation for more information.

### Source Directory
If no source directory is specified, `./src`, relative to the location of build.gradle is assumed. To specify an alternative source directory, set the `srcDir` property to the absolute path or relative path (based on the location of build.gradle) to the desired source directory. _**Do not use `~` in your path.** It may result in the build completing successfully even though nothing was built, as Gradle fails to find the specified source directory._ There are several ways to set properties on Gradle projects, but you're probably interested in knowing how to set them on the command line. To do this, add `-PsrcDir=/path/to/src` to your command.

### WPILib Version
Projects will always be built against WPILib 2016.5.1
