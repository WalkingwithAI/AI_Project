

# 超强AI音色克隆，CosyVoice，最新模型，超级快！



# 如何使用新模型？

### 一、 没有安装Cosyvoice：

**可参考Cosyvoice本地部署教程进行安装：[YouTube教程](https://www.youtube.com/watch?v=SMpGpDc0vHs&t=2s)，[Bilibili教程](https://www.bilibili.com/video/BV14S421R76v/?vd_source=6c8b8679b818b05d24c65f49a65eb994)**

安装之后，直接进行步骤2、步骤3、步骤4即可。

![视频封面YouTube](E:\Video Create\Cosyvoice最详细本地安装教程\视频封面YouTube.png)

## 二、已安装Cosyvoice项目

### **1. 更新项目代码**

``` 
#打开Cosyvoice项目文件夹后，在cmd中输入指令拉取最新代码
git pull
```

**PS：如果命令行执行过程中，一直提示unable to access 'https://github.com/......git' 、ConnectionError错误、SSLError，可以通过以下方法解决：**

（1）设置代理端口来克隆代码和下载三方库：

**代理端口地址需要通过kexue上网获取！**

设置方式：在cmd命令行窗口运行以下指令

set http_proxy=http://127.0.0.1:你的代理端口地址 & set https_proxy=http://127.0.0.1:你的代理端口地址

例如：

```
#设置代理端口地址
set http_proxy=http://127.0.0.1:11158 & set https_proxy=http://127.0.0.1:11158
```

然后执行项目代码克隆和安装三方库。

（2）没有魔法，可以手动下载项目代码文件，然后解压。如果需要更新项目，可将解压的文件夹内容覆盖到原有文件夹即可。

### **2.** **下载最新模型文件**

```
#激活cosyvoice虚拟环境
conda activate cosyvoice

#输入指令下载模型文件(需关闭魔法)
python -c "from modelscope import snapshot_download; snapshot_download('iic/CosyVoice-300M-25Hz', local_dir='pretrained_models/CosyVoice-300M-25Hz')"
```

### **3. 替换模型信息文件**

打开`CosyVoice\pretrained_models\CosyVoice-300M`，复制`spk2info.pt`文件，将其粘贴到`CosyVoice\pretrained_models\CosyVoice-300M-25Hz`文件夹内

### 4. 启动项目

制作批处理启动程序，双击运行。

```
@echo off
call conda activate cosyvoice
start http://127.0.0.1:50003
python webui.py --port 50003 --model_dir pretrained_models/CosyVoice-300M-25Hz
pause
```

**PS：**每次启动时可能加载一会儿，可等待一段时间。