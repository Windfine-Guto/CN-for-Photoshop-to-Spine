# CN-for-Photoshop-to-Spine
汉化了EsotericSoftware的Photoshop to Spine插件

## 安装  
  1.打开你的PS安装目录`Adobe Photoshop\Presets\Scripts`，将 PhotoshopToSpine.jsx 放入即可  
  2.重启PS完成安装

## 插件功能介绍  
[官方说明文档](https://github.com/EsotericSoftware/spine-scripts/tree/master/photoshop)  

  ![img](https://github.com/Windfine-Guto/CN-for-Photoshop-to-Spine/blob/main/covers/%E6%8F%92%E4%BB%B6%E4%B8%BB%E9%A1%B5%E9%9D%A2.png)  
#### 设置  
  • `忽略隐藏图层`不输出隐藏的组和图层。  
  • `忽略背景图层`不输出背景图层。  
  • `修建透明图层`选中后，将删除每个图层边缘周围的空格。取消选中时，所有图像都是 PSD 的大小。  
  • `写入Spine的JSON数据`编写了一个可以导入到 Spine 中的 JSON 文件。  
  • `创建盖印模板`将创建一个包含当前可见图层的图像，用作在 Spine 中定位的模板。类似于PS的盖印图层  
  • `调整缩放`在写入图像文件之前缩放图层。当在 Photoshop 中使用比您在 Spine 中使用的分辨率更高的艺术时，这很有用。  
  • `仅限选中图层`仅输出被选中的图层  
  • `像素填充`每个图像周围的像素数。这可以避免沿图像边缘的不透明像素出现锯齿伪影。  
    
  • `输出路径`将写入图像文件的文件夹。  
  • `JSON输出路径`如果结尾为 ，则将写入的 JSON 文件。否则，将使用 PSD 文件的名称写入 JSON 文件的文件夹。`.json`   
  
![img](https://github.com/Windfine-Guto/CN-for-Photoshop-to-Spine/blob/main/covers/%E5%B8%AE%E5%8A%A9%E9%A1%B5%E9%9D%A2.png)  
#### 标签  
方括号中的标签可用于图层和组名称以自定义输出。标签可以位于名称中的任何位置，例如 或 。如果省略，则使用图层或组名称。`head [slot][slot] head:name`  
  
##### 组和图层名称：  
  `[bone]`或层、槽和骨骼放置在骨骼下。骨骼在可见层的中心创建。骨骼组可以嵌套。`[bone:name]`  
  `[slot]`或图层放置在插槽中。[slot:name]  
  `[skin]`或图层放置在外观中。皮肤图层图像输出到皮肤的子文件夹中。`[skin:name]`  
  `[scale:number]`图层是缩放的。它们的附件是反向缩放的，因此它们在 Spine 中显示的大小相同。  
  `[folder]`或图层图像输出到子文件夹中。文件夹组可以嵌套。`[folder:name]`  
  `[overlay]`此图层用作以下所有图层的剪贴蒙版。  
  `[trim]`或强制此图层是否修剪空格。`[trim:false]`  
  `[mesh]`或层是网格，或者，如果指定了名称，则是链接网格。`[mesh:name]`  
  `[ignore]`图层、组和任何子组都不会输出。  

##### 组名称：  
  `[merge]`组中的图层将被合并并输出单个图像。  
  `[name:pattern]`为组中的图层名称添加前缀或后缀。模式必须包含星号 `（*）`。  

##### 图层名称：  
图层名称用于相对于任何父项或组的附件或蒙皮占位符名称。可以包含子文件夹。`[skin][folder]/`  
  `[path:name]`指定图层的图像文件名（如果需要与附件名称不同）。可用于具有 的组。`[merge]`  
如果图层名称、文件夹名称或路径名称以开头，则父图层不会影响该名称。`/`  

