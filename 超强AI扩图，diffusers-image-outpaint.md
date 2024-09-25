

# 超强AI扩图，diffusers-image-outpaint，全网最详细本地安装教程！



## 安装前提

**1. NVIDIA显卡，显存建议>=16G。8G和12G时也可运行，但会用到共享显存，稍慢**
![image-20240924115924868](https://github.com/user-attachments/assets/5c751b89-de4c-4915-95fd-182ea8867545)

**2. 安装、配置CUDA和cuDNN(已安装，可跳过)**

**3. 安装Git(已安装，可跳过)**

**4. 安装Conda(已安装，可跳过)**

如果未安装，可参考AI项目基本环境安装教程：[YouTube教程](https://youtu.be/yliAfNJgtpI?si=ODw5qKYQ5b9URA2c)，[Bilibili教程](https://www.bilibili.com/video/BV1seYteFEvy/?vd_source=6c8b8679b818b05d24c65f49a65eb994)
![视频封面ybt](https://github.com/user-attachments/assets/85574307-b95d-4b3f-927c-47c6a3b0a6bb)




## 项目安装指南

### **1. 克隆项目代码**

``` 
#克隆Huggingface代码需要打开魔法

git lfs install
git clone https://huggingface.co/spaces/fffiloni/diffusers-image-outpaint

#进入项目文件夹内
cd diffusers-image-outpaint
```

**PS1：如果命令行窗口执行过程中，一直提示SSLError或HTTPSConnectionError错误，可以设置使用代理端口克隆和下载三方库：**

**代理端口地址需要通过kexue上网获取！**

设置方式：在cmd命令行窗口运行以下指令

set http_proxy=http://127.0.0.1:你的代理端口地址 & set https_proxy=http://127.0.0.1:你的代理端口地址

例如：

```
#设置代理端口地址

set http_proxy=http://127.0.0.1:11157 & set https_proxy=http://127.0.0.1:11157
```

然后执行项目代码克隆和安装三方库。

**PS2：没有魔法，可手动下载完整项目包：[下载](https://wwaf.lanzouv.com/i3BEy2auxihg)**  **然后进入项目文件夹内，继续下面的操作。**

### **2.** **创建&激活虚拟环境**

```
#Python版本官方无要求，这里以常见的3.10.x为例

conda create -n diffusers-image-outpaint python=3.10 -y
conda activate diffusers-image-outpaint
```

### **3. 安装三方库**

```
#国外用户
pip install -r requirements.txt --extra-index-url https://download.pytorch.org/whl/cu118

#国内用户
pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple --extra-index-url https://download.pytorch.org/whl/cu118
```

**PS：如果文件下载过慢，可手动下载该文件后，重新激活虚拟环境，然后手动安装该库，速度会快很多。**

步骤：

手动下载该文件(可用浏览器、IDM或迅雷下载)，重新激活虚拟环境，运行手动安装指令：指令格式为

pip install 下载文件的完整路径 -i https://pypi.tuna.tsinghua.edu.cn/simple

例如：

pip install F:\AI\torch-2.0.1+cu118-cp38-cp38-win_amd64.whl -i https://pypi.tuna.tsinghua.edu.cn/simple

手动安装该库成功后，重新执行安装三方库指令(pip install -r requirements.txt......)，这样系统会继续安装别的库了，直到全部安装完。

### 4. 启动项目

制作批处理启动程序，双击运行。

```
@echo off
set HF_ENDPOINT=https://hf-mirror.com
:: 模型文件有近20G，可手动选择模型下载路径
set HF_HOME=G:\AI_Models
call conda activate diffusers-image-outpaint
start http://127.0.0.1:7860
python app.py
pause
```

初次启动时需要下载模型，可等待一段时间。

### PS：AI项目部署和使用问题，可加群一块交流
(1) Telegram: https://t.me/+hjgDJ5bwUzc4Yjdl

(2) 微信：
![AI项目安装和使用问题可加qun沟通](https://github.com/user-attachments/assets/569a4851-3266-4b78-ac86-bb043c4d0786)
