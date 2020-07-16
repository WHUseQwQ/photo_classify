#### 1������ĿĿ¼��ִ��
```
$ yarn add react-native-image-crop-picker
$ npx react-native link react-native-image-crop-picker
```
#### 2����android/build.gradle����
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
#### 3����android/app/build.gradle����
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
#### 4����android/app/src/main/AndroidManifest.xml����
```
<uses-permission android:name="android.permission.CAMERA" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
```
#### 5������ĿĿ¼��ִ��
```
$ npm install react-native-fs --save
$ npx react-native link react-native-fs
```
#### 6����android/app/build.gradle����
```
...
dependencies {
    ...
    implementation project(':react-native-fs')
}
```
#### 7��Ŀ¼��ִ��
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