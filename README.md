# Artifact Registry Gradle 6 issue.
Ticket: https://github.com/GoogleCloudPlatform/artifact-registry-maven-tools/issues/27

On Gradle 6 building :app will fail with:

A problem occurred evaluating project ':app'.
> Failed to apply plugin [id 'com.android.internal.application']
   > com.google.common.base.Suppliers$NonSerializableMemoizingSupplier cannot be cast to java.util.function.Supplier

(also happens on verified on 6.3 and 6.2)

# ~Artifact Registry config time issue~ (Fixed by artifactregistry-gradle-plugin:2.0.1)
Ticket: https://github.com/GoogleCloudPlatform/artifact-registry-maven-tools/issues/26

[Artifact Registry](https://github.com/GoogleCloudPlatform/artifact-registry-maven-tools) seems to auth for each of the subproject separatetly in a loop causing excessive configuration times.

Please remember to replace URL
```
url 'artifactregistry://us-west1-maven.pkg.dev/PROJECT_ID/REPOSITORY_ID'
```
in root `build.gradle` to test