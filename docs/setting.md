# Gradle
프로젝트의 Gradle 설정을 아래와 같이 설정하면 패키지를 사용할 수 있습니다.

```kotlin title="settings.gradle(Project)"
dependencyResolutionManagement {
  ...
  repositories {
    ...
    mavenCentral()
    maven(url = "https://jitpack.io")
  }
}
```

```kotlin title="build.gradle(App)"
dependencies {
  ...
  implementation("com.github.dongdongjae:android_package:<CURRENT_VERSION>")
}
```