## 项目运行前提：
1. 这个节点本身CPU可运行。如果需要结合其他节点，建议N卡，显存至少>=4G，越大越好；
2. 安装ComfyUI(已安装，可跳过)
如果未安装，可参考ComfyUI安装教程：
【AI图片】最强AI文生图项目，ComfyUI超详细本地安装教程，手把手教安装！_哔哩哔哩_bilibili
项目安装指南
1. 下载Comfyui官方启动包
下载后，使用7z相关工具解压缩。
下载地址：https://github.com/comfyanonymous/ComfyUI/releases/latest/download/ComfyUI_windows_portable_nvidia.7z
2. 下载模型
(1) 直接下载模型：
模型来源：开源项目官方Huggingface、Github、Civital(推荐)等站点
SD模型示例地址：https://civitai.com/api/download/models/127016?type=Model&format=SafeTensor&size=full&fp=fp16
下载后，可放在项目根目录下 \models\checkpoints或 \models\unet内，一般是前者。

(2) 导入秋叶大佬WebUI整合包的模型：
修改项目根目录下的extra_model_paths.yaml.example，文件名改成extra_model_paths.yaml。
以记事本打开文件，将base_path后面的内容改为秋叶SD_WebUI的项目根目录路径。
PS：注意不要删除“base_path: ”中冒号后面的空格符号，否则会导入失败。
3. 下载安装插件
安装Comfyui Manager插件：
打开插件地址，点击code，点击DownloadZIP，下载后解压缩。
打开进入ComfyUI_windows_portable根目录，打开ComfyUI\custom_nodes，
将Comfyui Manager插件的文件夹剪切到该文件夹内。
官方地址：https://github.com/ltdrdata/ComfyUI-Manager
4. 启动Comfyui：
点击run_nvidia_gpu.bat启动，等待一会，浏览器弹出程序界面
5. 安装汉化插件：
打开界面右侧的Manger，点击custom_nodes，搜索Translation，安装AIGODLIKE-COMFYUI-TRANSLATION，然后重启即可
6. 测试生成图片
加载默认工作流，选择模型，输入正向、反向提示词Prompt(使用默认的提示词也可)，然后点击右侧添加提示词队列，能正常生成图片，就代表安装成功了。

