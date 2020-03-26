# Artifact Registry config time issue
Ticket: https://github.com/GoogleCloudPlatform/artifact-registry-maven-tools/issues/26
[Artifact Registry](https://github.com/GoogleCloudPlatform/artifact-registry-maven-tools) seems to auth for each of the subproject separatetly in a loop causing excessive configuration times.

Please remember to replace URL
```
url 'artifactregistry://us-west1-maven.pkg.dev/PROJECT_ID/REPOSITORY_ID'
```
in root `build.gradle` to test


# Artifact Registry Gradle 6.2 issue.
Ticket: https://github.com/GoogleCloudPlatform/artifact-registry-maven-tools/issues/27
Change gradle-wrapper to 6.2
Building :app will fail with:

A problem occurred evaluating project ':app'.
> Failed to apply plugin [id 'com.android.internal.application']
   > com.google.common.base.Suppliers$NonSerializableMemoizingSupplier cannot be cast to java.util.function.Supplier
