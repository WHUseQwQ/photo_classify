## iOS����Ҫ�Ĳ���

�ο�

https://github.com/ivpusic/react-native-image-crop-picker#install  

https://blog.csdn.net/junhuahouse/article/details/89574511  

https://www.youtube.com/watch?v=ts9AM790NPQ&feature=youtu.be  

## ��׿����Ҫ�Ĳ���

#### 1������ĿĿ¼��ִ��
```
$ yarn add react-native-image-crop-picker
$ npx react-native link react-native-image-crop-picker
$ npm install native-base                           //������Ҫ
$ npx react-native link native-base                 //������Ҫ
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