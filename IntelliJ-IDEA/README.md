**Uncompleted**

<br/>

# IntelliJ IDEA

## Gradle project sync failed.

In ```1: Project``` panel, switch to ```Android``` view, and open ```gradle-wrapper.properties```:

``` INI
distributionBase=GRADLE_USER_HOME
distributionPath=wrapper/dists
zipStoreBase=GRADLE_USER_HOME
zipStorePath=wrapper/dists
distributionUrl=https\://services.gradle.org/distributions/gradle-4.1-all.zip
```

```GRADLE_USER_HOME```: Specifies the Gradle user home directory (which defaults to ```$USER_HOME/.gradle``` if not set).

So, go to ```%HOMEPATH%/.gradle/wrapper/dists/gradle-4.1-all/balabala/```, and we will found a .zip file and a .lck file here.
Try extracting that .zip file, some errors will be occur.
It meanings the compressed package is incomplete.
