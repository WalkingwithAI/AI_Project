

# 超强AI音效，Ezaudio，全网最详细本地安装教程！



## 安装前提

**1. NVIDIA显卡，显存建议>=12G。8G也可运行，但会用到共享显存，稍慢**
![image-20240924115924868](https://github.com/user-attachments/assets/d4582c64-574a-41bd-92c4-7faa86f10f4d)


**2. 安装、配置CUDA和cuDNN(已安装，可跳过)**

**3. 安装Git(已安装，可跳过)**

**4. 安装Conda(已安装，可跳过)**

如果未安装，可参考AI项目基本环境安装教程：[YouTube教程](https://youtu.be/yliAfNJgtpI?si=ODw5qKYQ5b9URA2c)，[Bilibili教程](https://www.bilibili.com/video/BV1seYteFEvy/?vd_source=6c8b8679b818b05d24c65f49a65eb994)
![视频封面ybt](https://github.com/user-attachments/assets/e919f124-3bb3-494f-9a1c-3000f9839b78)


## 项目安装指南

### **1. 克隆项目代码**

``` 
#安装git lfs
git lfs install

#忽略大文件下载
set GIT_LFS_SKIP_SMUDGE=1

#克隆项目代码(国外用户)
git clone https://huggingface.co/spaces/OpenSound/EzAudio

#克隆项目代码(国内用户)
git clone https://hf-mirror.com/spaces/OpenSound/EzAudio

#进入项目根目录文件夹内
cd EzAudio
```

**PS1：如果命令行窗口执行过程中，一直提示SSLError或HTTPSConnectionError错误，可以设置使用代理端口克隆和下载三方库：**

**代理端口地址需要通过kexue上网获取！**

设置方式：在cmd命令行窗口运行以下指令

set http_proxy=http://127.0.0.1:你的代理端口地址 & set https_proxy=http://127.0.0.1:你的代理端口地址

例如：

```
#设置代理端口地址

set http_proxy=http://127.0.0.1:11158 & set https_proxy=http://127.0.0.1:11158
```

然后执行项目代码克隆和安装三方库。

### **2.** **创建&激活虚拟环境**

```
#Python版本官方无要求，这里以常见的3.10.x为例

conda create -n Ezaudio python=3.10 -y
conda activate Ezaudio
```

### **3. 安装三方库**

在项目根目录文件夹内操作：

```
#国外用户
conda install -c conda-forge ffmpeg
pip install gradio
pip install -r requirements.txt --extra-index-url https://download.pytorch.org/whl/cu118

#国内用户
conda install -c -y conda-forge ffmpeg
pip install gradio -i https://pypi.tuna.tsinghua.edu.cn/simple
pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple --extra-index-url https://download.pytorch.org/whl/cu118
```

**PS：如果文件下载过慢，可手动下载该文件后，重新激活虚拟环境，然后手动安装该库，速度会快很多。**

步骤：

手动下载该文件(可用浏览器、IDM或迅雷下载)，重新激活虚拟环境，运行手动安装指令：指令格式为

pip install 下载文件的完整路径 -i https://pypi.tuna.tsinghua.edu.cn/simple

例如：

pip install F:\AI\torch-2.0.1+cu118-cp38-cp38-win_amd64.whl -i https://pypi.tuna.tsinghua.edu.cn/simple

手动安装该库成功后，重新执行安装三方库指令(pip install -r requirements.txt......)，这样系统会继续安装别的库了，直到全部安装完。

### 4. 下载模型

在项目根目录文件夹内操作：

```
#国外用户
git lfs pull

#国内用户
set HF_ENDPOINT=https://hf-mirror.com
git lfs pull
```

### 5. 修改代码

搜索`spaces`，将相关代码删除或注释掉。

```
import spaces
@spaces.GPU
@spaces.GPU
```

### 6. 启动项目

制作批处理启动程序，双击运行。

```
#国外用户
@echo off
call conda activate Ezaudio
start http://127.0.0.1:7860
python app.py
pause

#国内用户
@echo off
set HF_ENDPOINT=https://hf-mirror.com
call conda activate Ezaudio
start http://127.0.0.1:7860
python app.py
pause
```

**PS：**每次启动时可能加载一会儿，可等待一段时间。

