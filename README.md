# tinyImgUpload
一个灵活的图片上传插件，支持预览和异步上传图片，并且不依赖jQuery等js库。   
A flexible and independent image upload plugin that can preview and upload image asynchronously.   

## 使用方法   
执行tinyImgUpload方法   
tinyImgUpload(ele, options)   
@param ele [string] [生成组件的元素的选择器]    
@param options [Object] [对组件设置的基本参数]   
options具体参数如下   
 * path 图片上传的地址路径 必需
 * onSuccess(res) 文件上传成功后的回调 参数为返回的文本 必需
 * onFailure(res) 文件上传失败后的回调 参数为返回的文本 必需   
 
@return [function] [执行图片上传的函数]
 
示例   
用户引入插件代码后，只需要像下面这样，设置一些参数，然后执行一个方法就生成一个图片上传组件。
```
<div id="upload"></div>  // 这是用来生成图片上传组件的div
```
```
<script>
// 设置参数
var options = {
    path: '/',    // 上传图片时指定的地址路径，类似form变淡的action属性
    onSuccess: function (res) {    // 上传成功后执行的方法，res是接收的ajax响应内容
        console.log(res);  
    },
    onFailure: function (res) {    // 上传失败后执行的方法，res是接收的ajax响应内容
        console.log(res);
    }
}
// 执行生成图片上传插件的方法, 第一个参数是上面提到的准备生成组件的div选择器，第二个参数是设置的组件信息，执行方法后返回一个函数指针，指向执行上传功能的函数，通过把执行上传功能的函数暴露出来，用户就可以自己控制何时上传图片了。
var upload = tinyImgUpload('#upload', options);  
</script>
```   
