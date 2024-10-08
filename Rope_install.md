# (1)Python：

下载地址(需下载V3.10.x系列)：https://www.python.org/downloads/

命令行指令：

\# 检查Python版本(Python 3.10.X)

python --version

# (2)CUDA：

下载地址(需下载显卡支持的版本，且大于等于V11.8)：https://developer.nvidia.com/cuda-toolkit-archive

\# 检查显卡支持的最大CUDA版本命令行指令

nvidia-smi

# (3)cuDNN：

下载地址(需下载CUDA支持的版本，且大于等于V8.5)：https://developer.nvidia.com/rdp/cudnn-archive

\# 检查是否安装CUDA成功的命令行指令

nvcc -V

# (4)FFmpeg：

下载地址：https://ffmpeg.org/download.html

# (5)Rope：

下载地址：https://github.com/Hillobar/Rope

# (6)Rope命令行指令：

\# 新建虚拟环境

python.exe -m venv venv

\# 激活虚拟环境

.\venv\Scripts\activate

\# 安装Rope的三方库

国外安装指令：.\venv\Scripts\pip.exe install -r .\requirements.txt

国内安装指令：.\venv\Scripts\pip.exe install -r .\requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple

PS：如果torch-2.0.1+cu118-cp310-cp310-win_amd64.whl下载过慢，可手动下载该文件后，重新激活虚拟环境，然后手动安装该库，速度会快很多。

步骤：

手动下载该文件(可用浏览器、IDM或迅雷下载)，文件地址：https://download.pytorch.org/whl/cu118/torch-2.0.1%2Bcu118-cp310-cp310-win_amd64.whl

重新激活虚拟环境，运行手动安装指令：指令格式为pip install 下载文件的完整路径 -i https://pypi.tuna.tsinghua.edu.cn/simple

例如：pip install F:\AI\CosyVoice-main\CosyVoice-main\torch-2.0.1+cu118-cp38-cp38-win_amd64.whl -i https://pypi.tuna.tsinghua.edu.cn/simple

手动安装该库成功后，重新执行(6)中的安装三方库指令，这样系统会继续安装别的库了，直到全部安装完。

# (7)Rope模型：

下载地址(珍珠版共16个模型)：https://github.com/Hillobar/Rope/releases/tag/Sapphire

也可用百度云下载：https://pan.baidu.com/s/155yBVv6G0DfXnSgZMRwW7A?pwd=asg6 

提取码：asg6

### PS：AI项目部署和使用问题，可加群一块交流
(1) Telegram: https://t.me/+hjgDJ5bwUzc4Yjdl

(2) 微信：
![AI项目安装和使用问题可加qun沟通](https://github.com/user-attachments/assets/569a4851-3266-4b78-ac86-bb043c4d0786)
