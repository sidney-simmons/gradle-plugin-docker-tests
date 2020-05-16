# gradle-plugin-docker-tests

gradle-plugin-docker-tests is a gradle project meant for testing the [gradle-plugin-docker](https://github.com/sidney-simmons/gradle-plugin-docker) plugin.

## Usage

Clone the plugin repository and execute `./gradlew build`.  Then execute `./gradlew publish`.  This will publish the plugin to a local maven repository directory `[PLUGIN PROJECT ROOT]/build/test-maven-repo`.  Now you can use the local plugin in this project by setting the following in this project's build files.

> build.gradle

``` gradle
plugins {
    id 'com.sidneysimmons.gradle-plugin-docker' version '[PLUGIN VERSION]'
}
```

> settings.gradle

``` gradle
pluginManagement {
    repositories {
        maven {
            url '[PLUGIN PROJECT ROOT]/build/test-maven-repo'
        }
        gradlePluginPortal()
    }
}
```

## License
[MIT](https://choosealicense.com/licenses/mit/)