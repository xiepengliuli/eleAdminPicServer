
# 安装JDK1.7或1.8
  注意：别忘记配置环境变量

# 解压压缩包，进去启动tomcat
## 启动验证：http://localhost:28080/jsp/controller.jsp?action=config  ##
返回结果如下：
```{
	videoMaxSize: 102400000,
    videoActionName: "uploadvideo",
    fileActionName: "uploadfile",
    fileManagerListPath: "/ueditor/jsp/upload/file/",
    imageCompressBorder: 1600,
    imageManagerAllowFiles: [
    ".png",
    ".jpg",
    ".jpeg",
    ".gif",
    ".bmp"
    ],
    imageManagerListPath: "/ueditor/jsp/upload/image/",....
```
## eleAdmin中的配置： ##
### ueditor.config.js 
serverUrl: "http://localhost:28080/jsp/controller.jsp"\

### demo_attachment/add.vue
             <el-upload 
              class="upload-demo"
              action="http://localhost:28080/jsp/controller.jsp?action=uploadfile"
              :on-success="handleSuccess"
              :on-preview="handlePreview"
              :on-remove="handleRemove"
              :file-list="fileList">
              <el-button size="small" type="primary">点击上传</el-button>
              <div slot="tip" class="el-upload__tip">只能上传jpg/png文件，且不超过500kb</div>
           </el-upload>
