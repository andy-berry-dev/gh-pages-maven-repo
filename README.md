github-maven-repo
=======================

- Prerequisites: Gradle installed locally

### Deploying an Artifact
1. To find the required arguments run `./gradlew`
2. Download the Artifact to the root of the git repo directory (e.g. `github-maven-repo`)
3. Run `gradle -PdepGroup=org.my.group -PdepVersion=1.2.3 -PdepArtifact=someArtifact -PdepExtension=<artifact extension> -PdepFile=<path to file>`
4. Delete the file downloaded in step 2
5. Commit and push the new artifacts inside `repo`
