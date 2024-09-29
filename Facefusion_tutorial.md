# AI换脸，Facefusion 3.0，N卡本地部署教程！



## 一、安装前提(NVIDIA显卡)

**1. 显存>=4G**

打开任务管理器，选择性能，查看右侧专用显卡显存，要>=4G。
![image](https://github.com/user-attachments/assets/f9e505a8-feee-4998-9c84-615cc813101c)

**2. 显卡可以支持CUDA12.4版本**

cmd窗口输入`nvidia-smi`，支持CUDA版本>=12.4即可。否则，尝试更新显卡驱动后再试。
![image-20240924120332212](https://github.com/user-attachments/assets/4a40e5b4-89bf-48e7-8a83-bdbb07c6db6f)

**3. 安装Git(已安装，可跳过)**

**4. 安装Conda(已安装，可跳过)**

如果以上软件未安装，可参考AI项目基本环境安装教程：[YouTube教程](https://youtu.be/yliAfNJgtpI?si=ODw5qKYQ5b9URA2c)，[Bilibili教程](https://www.bilibili.com/video/BV1seYteFEvy/?vd_source=6c8b8679b818b05d24c65f49a65eb994)

![视频封面ybt](https://github.com/user-attachments/assets/d5d6a14f-0711-4889-b04a-60c134b45d05)


## 二、facefusion 3.0安装指南

### **1. 克隆项目代码**

``` 
#克隆代码
git clone https://github.com/facefusion/facefusion.git

#进入项目文件夹内
cd facefusion
```

**PS：如果命令行窗口执行过程中，一直提示SSLError或HTTPSConnectionError错误，可以设置使用代理端口克隆和下载三方库：**

**代理端口地址需要通过kexue上网获取！**

设置方式：在cmd命令行窗口运行以下指令

set http_proxy=http://127.0.0.1:你的代理端口地址 & set https_proxy=http://127.0.0.1:你的代理端口地址

例如：

```
#设置代理端口地址

set http_proxy=http://127.0.0.1:11157 & set https_proxy=http://127.0.0.1:11157
```

再继续执行项目代码克隆和安装三方库。

### **2.** **创建&激活虚拟环境**

```
#官方推荐Python版本3.10系列

conda create --name facefusion python=3.10 -y
conda activate facefusion
```

### **3. 安装三方库**

```
#安装cuda12.4 cuDNN9.2
conda install -y conda-forge::cuda-runtime=12.4.1 conda-forge::cudnn=9.2.1.18

#(可选)4070以上算力显卡可安装tensorrt
pip install tensorrt==10.4.0 --extra-index-url https://pypi.nvidia.com

#安装其他库、配置到系统环境变量
conda install -y -c conda-forge ffmpeg
python install.py --onnxruntime cuda
```

**PS：如果命令行窗口执行过程中，一直提示SSLError或HTTPSConnectionError错误，可以设置使用代理端口克隆和下载三方库：**

**代理端口地址需要通过kexue上网获取！**

设置方式：在cmd命令行窗口运行以下指令

set http_proxy=http://127.0.0.1:你的代理端口地址 & set https_proxy=http://127.0.0.1:你的代理端口地址

例如：

```
#设置代理端口地址

set http_proxy=http://127.0.0.1:11157 & set https_proxy=http://127.0.0.1:11157
```

再继续执行项目代码克隆和安装三方库。

### 4. 模型下载

界面上选择不同功能，会自动下载相应模型，但是速度非常慢。

建议手动下载需要的模型，然后放置到`facefusion\.assets\models`中，没有`.assets`文件夹，就需要新建一个。

**模型下载地址(可以开魔法使用IDM或迅雷下载，更快)：**

```
https://github.com/facefusion/facefusion-assets/releases/tag/models-3.0.0
```

**facefusion常见模型文件(百度云)：**
https://pan.baidu.com/s/12JdPYVOG9idCt_TaHPYm7Q?pwd=bk3q 提取码: bk3q

### 5. 启动项目

制作批处理启动程序，双击运行。

```
@echo off
call conda activate facefusion
start http://127.0.0.1:7860
python facefusion.py run
pause
```

### 参考资料

[1] facefusion官方Github：https://github.com/facefusion/facefusion

[2] facefusion官方Help主页：https://docs.facefusion.io/installation

### PS：AI项目部署和使用问题，可加群一块交流
(1) Telegram: https://t.me/+hjgDJ5bwUzc4Yjdl

(2) 微信：
![AI项目安装和使用问题可加qun沟通](https://github.com/user-attachments/assets/569a4851-3266-4b78-ac86-bb043c4d0786)


