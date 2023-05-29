# sample-gradle-package

sampling publish gradle package on github

## General documentation

- <https://docs.gradle.org/current/userguide/build_init_plugin.html#sec:kotlin_library>
- <https://docs.github.com/en/actions/publishing-packages/publishing-java-packages-with-gradle>
- <https://stackoverflow.com/questions/57323260/how-to-push-to-github-package-registry-with-gradle/58206431?stw=2#58206431>
- <https://docs.gradle.org/current/samples/sample_publishing_credentials.html>
- <https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-gradle-registry#authenticating-with-a-personal-access-token>

## Creating tokens and configuring secrets

- <https://docs.github.com/en/actions/security-guides/encrypted-secrets>
- <https://github.com/settings/tokens/new>
- https://github.com/<OWNER>/<REPO>/settings/secrets/actions

## publishing workflow

in order to create a package into the registry, there is a github action to call `./gradlew publish`.

simply `git tag <version>`, push the tag and the workflow will kick in.

The publish command can be called directly from dev environment, just provide the needed variables:

```bash
GITHUB_ACTOR=<your github username>
GITHUB_TOKEN=<your personal access token>
GIT_TAG=<the desired tag>
```

except for `GIT_TAG`, those values are provided by github actions environment.

## using the package

see [this project](https://github.com/sombriks/using-sample-gradle-package)

## further enhancements

add a release in the github page containing the artifacts present on github package registry
