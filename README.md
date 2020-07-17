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
如要自行添加随机的背景图库，只要将图片导入到imgBackground文件夹中，并在img_arr.js中添加
export default{
    img1:require('./imgBackgrond/bighead.png'),
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
