# HivisionIDPhotos_ComfyUI本地安装教程



## 安装前提

**1. 需安装ComfyUI(已安装，可跳过)**

如果未安装，可参考ComfyUI本地安装教程：[YouTube教程](https://youtu.be/yliAfNJgtpI?si=h0IqM1_-GUjB7R-2)，[Bilibili教程](https://www.bilibili.com/video/BV1SiHue9E4h/?vd_source=6c8b8679b818b05d24c65f49a65eb994)




## 安装指南

**1. 安装项目节点**

打开ComfyUI，打开Manager管理器，搜索并安装HivisionIDPhotos节点。

安装后重启ComfyUI，系统自动下载需要的Python三方库，等窗口加载完后即可。

**2. 下载工作流**

工作流地址：[HivisionIDPhotos-ComfyUI](https://github.com/AIFSH/HivisionIDPhotos-ComfyUI)，下载工作流json文件。

**3. 下载模型权重**

**抠图模型：**

- `modnet_photographic_portrait_matting.onnx` (24.7MB): [点击下载](https://github.com/Zeyi-Lin/HivisionIDPhotos/releases/download/pretrained-model/modnet_photographic_portrait_matting.onnx)
- `hivision_modnet.onnx` (24.7MB): [点击下载](https://github.com/Zeyi-Lin/HivisionIDPhotos/releases/download/pretrained-model/hivision_modnet.onnx)
- `rmbg-1.4.onnx` (176.2MB):后重命名为`rmbg-1.4.onnx`。 [点击下载](https://huggingface.co/briaai/RMBG-1.4/resolve/main/onnx/model.onnx?download=true)
- `birefnet-v1-lite.onnx`(224MB):下载后重命名为`birefnet-v1-lite.onnx`。 [点击下载](https://github.com/ZhengPeng7/BiRefNet/releases/download/v1/BiRefNet-general-bb_swin_v1_tiny-epoch_232.onnx)

全部下载后，将文件存到项目的`ComfyUI/custom_nodes/HivisionIDPhotos-ComfyUI/hivision/creator/weights`目录下。

**人脸检测模型：**

RetinaFace：下载后放到`hivision/creator/retinaface/weights`目录下。[点击下载](https://github.com/Zeyi-Lin/HivisionIDPhotos/releases/download/pretrained-model/retinaface-resnet50.onnx)

**4. 启动**

打开ComfyUI，加载对应的工作流，选择上传图片，调整需要的参数，点击生成即可。




## 参考资料

[1] 项目地址：[HivisionIDPhotos](https://github.com/Zeyi-Lin/HivisionIDPhotos)，感谢[Zeyi-Lin](https://github.com/Zeyi-Lin/HivisionIDPhotos/commits?author=Zeyi-Lin)大佬制作。

[2] 工作流地址：[HivisionIDPhotos-ComfyUI](https://github.com/AIFSH/HivisionIDPhotos-ComfyUI)，感谢[AIFSH](https://github.com/AIFSH)大佬提供。


