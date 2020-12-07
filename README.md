LCEDA图片转换器

作者：矛盾聚合体 & Kearney

简介：可将图片转换为立创EDA的PCB库文件，然后在立创EDA中以导入库的方式导入图像。
优点是导入后的图片较立创EDA自带的图片工具清晰度更高更细腻。

![win10下效果预览][1]
![avatar](https://image.lceda.cn/pullimage/2sn0T1YLOZSa1gTZYOoLbB2pJrnzIGx8H9TDlWlr.png)
# 使用说明
- 处理图片：参考[PCB照片_附带生成脚本](https://lceda.cn/Knight_Sin/PCBzhao-pian)，非必需，当然处理后更好看。
- 生成LIB：启动程序后，点击选取文件选取要转换的图片文件（当前仅支持一次一张），然后对各个参数进行修改，不修改将保持默认参数，设置好参数后点击生成图片，生成完成之后会弹出提示框提示转换完成，生成的Lib位于所选择图片相同目录下。  
- 导入LIB：打开立创EDA编辑器，在顶部菜单栏依次选择 -> “文件”-“打开”-“立创EDA”，然后选择刚才生成的LIB_xxx.json文件，在EDA中会打开库编辑器，删掉多余的图层，保存即可。
- PCB高清晰绘图：在PCB绘制界面，在左侧菜单栏依次选择 -> “元件库”-"立创EDA"-"封装",即可导入图片。
# 程序下载方式
GUI_v0.0.1版本的图片拖动功能**暂未完善**、请使用‘选择文件’功能选取图片文件。程序是免安装的，解压双击main.exe即可运行。

## 方法一：下载程序
windows、Linux已经编译好的程序（By pyinstaller）见Release或者百度网盘

[20201201win+linuxV0.0.0 提取码: yirq](https://pan.baidu.com/s/1uG6g0DEBkowuJXRK9za9VA)
[20201204win+linux_GUI_v0.0.1 提取码: d16s](https://pan.baidu.com/s/1RLmTxRCp_XaVfVA_X4VKsA )
## 方法二：自行编译
### 环境准备
- 安装python3
```bash
# linux
$ sudo apt install python3
```
- 安装依赖包：opencv、numpy、pyqt5
```bash
$ pip3 install numpy
$ pip3 install opencv-python
$ pip3 install pyqt5
```
### 克隆代码、运行
```bash
$ git clone git@github.com:KnightSin/PIC2LCEDA.git
$ cd PIC2LCEDA
$ python3 main.py
```
# 贡献方式
入门：点赞右上角Star点一下。  
修Bug和改进：准备依赖环境和Qt designer，fork本仓库，修改bug，一个issus(最小修改单位)一次commit。  
脚本哥：将本程序修改为js脚本作为浏览器插件（期待大佬ing）
# License
GPL-3.0 License
# Reference
- [PCB照片_附带生成脚本](https://lceda.cn/Knight_Sin/PCBzhao-pian)
- [立创EDA文档格式-标准版](https://docs.lceda.cn/cn/DocumentFormat/EasyEDA-Format-Standard/index.html)
- [no module named cv2](https://www.cnblogs.com/zjutzz/p/11944662.html)

[1]:data:image/png;base64,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
