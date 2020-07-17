## 项目配置

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

## 字体文件导入

```
将两个ttf字体文件放入.\android\app\src\main\assets\fonts目录下
```
## 应用图标文件导入
```
将res.zip解压，将文件覆盖.\android\app\src\main\res目录下的文件
```
## 背景图片文件导入
```
将imgBackground目录下载到项目文件中，将img_arr.js下载到项目中
如要自行添加随机的背景图库，只要将图片导入到imgBackground文件夹中，并在img_arr.js中添加(最好在图形编辑器中将透明度降低至60以下)
export default{
    img1:require('./imgBackground/bighead.png'),
    img2:require('./imgBackground/background1.jpg'),
    ...
    //ADD your picture
    imgn:require('./imgBackground/pictureName'),
    .....
};
并在生成随机数的函数中修改随机数范围
class HomeScreen extends Component {
......
    render(){
        return(
        <ImageBackground style={styles.backgroundImage}
        source={img_arr['img'+getRandom1(1,n)]}>  //Change 'n' here
        ......
        )
    }
......
}

```