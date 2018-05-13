**Uncompleted**

<br/>

# IntelliJ IDEA

## Gradle project sync failed.

Open or create an android project, you will see a tip says "Gradle projects need to be imported" with two choices ```Import Changes``` and ```Enable Auto-Import```.
Click ```Import Changes```, and intelliJ IDEA will download the files of Gradle.

But, in general, a error tip will appear in a while.
It says "...Gradle project sync failed...", how to solve it?

In ```1: Project``` panel, switch to ```Android``` view, and open ```gradle-wrapper.properties```:

``` INI
distributionBase=GRADLE_USER_HOME
distributionPath=wrapper/dists
zipStoreBase=GRADLE_USER_HOME
zipStorePath=wrapper/dists
distributionUrl=https\://services.gradle.org/distributions/gradle-4.1-all.zip
```

```GRADLE_USER_HOME```: Specifies the Gradle user home directory (which defaults to ```$USER_HOME/.gradle``` if not set).

So, go to ```%HOMEPATH%/.gradle/wrapper/dists/gradle-4.1-all/balabala/```, and we will find a .zip file and a .lck file here.
Try extracting that .zip file, some errors will be occur.
It meanings the compressed package is incomplete.

## The supplied javaHome seems to be invalid.

And then, when you re-click the ```Refresh Gradle project``` button in ```Build``` panel, a error will appear and it says "The supplied javaHome seems to be invalid. I cannot find the java executable. Tried location: ..."

"..." will be "%Your_SDK_Folder%\bin\java.exe". But my %JAVA_HOME% is correct, what happended?

Go to ```File``` - ```Settings``` - ```Build, Execution, Deployment``` - ```Build Tools``` - ```Gradle```, find entry named ```Gradle JVM```, we will find the current setting is incorrect (```Use Project JDK(path: %My_SDK_Folder%)```).
Choose ```Use JAVA_HOME```, and click "OK".

solved.

## Reference

* [Android Studio 首坑 Gradle sync failed: Cause: error in opening zip file 的错误 - 梁乔峰 - 博客园](https://www.cnblogs.com/maydear/p/6849745.html)
* [](https://stackoverflow.com/a/36539783/9418981)
