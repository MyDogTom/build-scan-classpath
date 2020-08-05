# build-scan-classpath

Show case project for https://discuss.gradle.org/t/class-path-has-changed-after-adding-scan/30038

**Gradle 5.0 , Kotlin 1.3.10**
Steps to reproduce:

```
>./gradlew clean
>...
>BUILD SUCCESSFUL in 0s
>1 actionable task: 1 up-to-date
>
>./gradlew build
>...
>BUILD SUCCESSFUL in 2s
>10 actionable tasks: 10 executed
>
>./gradlew build
> ...
>BUILD SUCCESSFUL in 0s
>10 actionable tasks: 2 executed, 8 up-to-date
>
>./gradlew build --scan
>...
>BUILD SUCCESSFUL in 1s
>10 actionable tasks: 5 executed, 5 up-to-date
https://gradle.com/s/jgvac4sm4f57e
```

Task "compileKotlin" was not up-to-date: https://scans.gradle.com/s/jgvac4sm4f57e/timeline?outcomeFilter=SUCCESS&outcomeFilter=FAILED&task=ta44irykic3pc

**Gradle 6.5-rc-5 , Kotlin 1.3.72**

```
>./gradlew clean
>...
>BUILD SUCCESSFUL in 0s
>1 actionable task: 1 up-to-date
>
>./gradlew build
>...
>BUILD SUCCESSFUL in 7s
>8 actionable tasks: 8 executed
>
>./gradlew build
> ...
>BUILD SUCCESSFUL in 711ms
>8 actionable tasks: 8 up-to-date
>
>./gradlew build --scan
>...
>BUILD SUCCESSFUL in 4s
>8 actionable tasks: 3 executed, 5 up-to-date
https://gradle.com/s/llomqm4pznaem
```
