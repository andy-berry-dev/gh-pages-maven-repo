# gh-pages-maven-repo

## Overview

A small Gradle build script to deploy build artifacts to a 'repo' directory in a Maven format. The repo can then be hosted on `gh-pages` for free and used as a Maven repository by any other build scripts.

## Requirements

A java virtual machine in order to run the Gradle Wrapper. Gradle, which is required to run the build script, will be downloaded automatically by the Gradle wrapper (`gradlew`).

## Usage

1. Fork the project and clone locally.
1. Download the file that should be added to the Maven repo.
1. Run `./gradlew -PdepGroup=<GROUP.NAME> -PdepVersion=<VERSION> -PdepArtifact=<ARTIFACT.NAME> -PdepFile=<PATH.TO.FILE>` which will 'upload' the file to the 'repo' directory.
  - For example `./gradlew -PdepGroup=com.my.company -PdepVersion=1.3.8-0 -PdepArtifact=MyCoolArtifact -PdepFile=/home/me/MyCoolArtifact.jar`.
1. `git commit` and `git push` as you normally would do any other changes to a Git repo. Make sure this is to the `gh-pages` branch so it's hosted on GitHub.
1. Use `http://<github-user>.github.io/<repo-name>/` as the Maven repository and the corresponding group, artifact name and version in your build scripts.

## Example

The [BladeRunnerJS](http://bladerunnerjs.org) project uses this approach to host it's build dependencies that are not hosted on Maven central. See [github.com/BladeRunnerJS/brjs-build-dependencies](http://github.com/BladeRunnerJS/brjs-build-dependencies) for the souce. The repo itself is then hosted at [bladerunnerjs.github.io/brjs-build-dependencies/repo](http://bladerunnerjs.github.io/brjs-build-dependencies/repo)