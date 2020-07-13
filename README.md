## iOS端需要的操作

参考

https://github.com/ivpusic/react-native-image-crop-picker#install  

https://blog.csdn.net/junhuahouse/article/details/89574511  

https://www.youtube.com/watch?v=ts9AM790NPQ&feature=youtu.be  

## 安卓端需要的操作

#### 1、在项目目录下执行
```
$ yarn add react-native-image-crop-picker
$ npx react-native link react-native-image-crop-picker
$ npm install native-base                           //好像不需要
$ npx react-native link native-base                 //好像不需要
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