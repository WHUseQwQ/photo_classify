#### 1、在项目目录下执行
```
$ yarn add react-native-image-crop-picker
$ npx react-native link react-native-image-crop-picker
```
#### 2、在android/build.gradle插入
```
allprojects {
    repositories {
      mavenLocal()
      jcenter()
      maven { url "$rootDir/../node_modules/react-native/android" }

      // ADD THIS
      maven { url 'https://maven.google.com' }
    
      // ADD THIS
      maven { url "https://www.jitpack.io" }
    }
}
```
#### 3、在android/app/build.gradle插入
```
android {
    ...

    defaultConfig {
        ...
        vectorDrawables.useSupportLibrary = true
        ...
    }
    ...
}
```
#### 4、在android/app/src/main/AndroidManifest.xml插入
```
<uses-permission android:name="android.permission.CAMERA" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
```
#### 5、在项目目录下执行
```
$ npm install react-native-fs --save
$ npx react-native link react-native-fs
```
#### 6、在android/app/build.gradle插入
```
...
dependencies {
    ...
    implementation project(':react-native-fs')
}
```
#### 7、目录下执行
```
$ npm install @react-navigation/native
$ npx react-native link @react-navigation/native
$ npm install react-native-reanimated react-native-gesture-handler react-native-screens react-native-safe-area-context @react-native-community/masked-view
$ npx react-native link react-native-reanimated
$ npx react-native link react-native-gesture-handler
$ npx react-native link react-native-screens
$ npx react-native link react-native-safe-area-context
$ npx react-native link @react-native-community/masked-view
$ npm install @react-navigation/stack
```