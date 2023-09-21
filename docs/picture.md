# nonebot_plugin_kokomi 图片界面自定义教程

## 图片生成逻辑

kokomi是通过python代码的方式通过修改图片实现图片生成，而不是通过浏览器渲染html文件，不需要前端的知识

整个代码逻辑就是：
1. 读取对应功能的背景图片
2. 往图片上添加文字和图片
3. 导出处理好的图片

所以，在插件的 `nonebot_plugin_kokomi/scripts/png` 文件夹内，你会看到所有功能的背景图片以及其他图片的预制件

在python代码上，主要使用了两个模块：

- pillow(pil): 实现往图片上添加文字和形状
- opencv-python(cv2): 实现往背景图片上叠加图片

> 之所以会使用到cv2模块，是因为pil模块在实现图片叠加时，img.paste函数处理png图片时会丢失图片的alpha通道

## 背景图片生成

背景图片是先通过 `Photoshop` 设计再到导出为png图片，那么就可以通过背景图片的psd文件来实现修改背景图片页面

例如以 wws me 功能为例，修改背景文件样式：
1. 去开发者群内下载对应的wws_basic.psd
2. 使用 Photoshop 打开psd文件
3. 修改图片样式，例如添加一些二次元图片，请注意修改添加图片的透明度
4. 导出png替换原背景图片文件（nonebot_plugin_kokomi/scripts/png/background/wws_basic.png）

## 修改图片字体

kokomi目前采用了两种字体，如果也可以更改为自己喜欢的字体，步骤如下：
1. 打开data_source.py文件（nonebot_plugin_kokomi/scripts/data_source.py）
2. 修改 `font1_path` `font2_path` 对应的字体文件即可实现修改字体

## 图片生成代码

下面以 wws me info 功能为例，详细介绍一下图片生成的逻辑

> 文件：nonebot_plugin_kokomi/scripts/wws_info.py

文件内有两个主要函数：

1. main函数：通过数据生成图片
2. get_png函数：请求和处理数据，生成图片的导出

下面详细介绍一下main函数的图片处理的几个步骤
### 1 list变量
```python
text_list = []
box_list = []
```
在main函数的开头会看到两个重要的list变量

主要作用是存储需要在图片添加文字或形状的信息（位置大小等），具体参数会在后面介绍

### 2 读取背景图片
```python
image_list = os.listdir(os.path.join(file_path, 'png', 'background_info'))
random_image = random.choice(image_list)
res_img = cv2.imread(os.path.join(file_path, 'png', 'background_info', random_image), cv2.IMREAD_UNCHANGED)
res_img = cv2.resize(res_img, None, fx=0.8, fy=0.8)
```
读取背景图片，从background_info文件夹随机抽取一个背景图片（实现随机背景的功能）

通过cv2.imread的方式读取png图片，通过cv2.resize的方式对图片进行大小的缩放（长宽变为原来的0.8）

### 3 图片文字的添加

```python
# Id卡
fontStyle = font_list[1][100]                                                   # 文字字体
if result['data']['clans']['clan'] == {}:                                       # 用户未加入工会的tag
    tag = '[]'
    tag_color = (179, 179, 179)
else:                                                                           # 用户未加入工会的tag
    tag = '['+result['data']['clans']['clan']['tag']+']'
    tag_color = clan_color[result['data']['clans']['clan']['color']]
text_list.append([(160, 100), tag, tag_color, 1, 100])                          # 在图片上添加用户工会的tag
w = x_coord(tag, fontStyle)                                                     # 获取tag文字的长度
text_list.append([(160+w+20, 100), result['nickname'], (0, 0, 0), 1, 100])      # 在tag文字后添加用户的id
```
上述代码主要是往info图片背景上添加用户工会和id，例如：[TIF-K] SangonomiyaKokomi_

**text_list参数的解释：**
```python
text_list.append([              # 往text_list中写入需要写入文字的数据

    (160+w+20, 100),            # 文字左上角的坐标
    result['nickname'],         # 需要添加的文字
    (0, 0, 0),                  # 文字的颜色
    1,                          # 字体的类型
    100                         # 字体的大小

])
```
后续所有文字都是通过这个方式写入text_list

**x_coord函数的解释：**
```python
w = x_coord(       # w表示文字在图片上的长度（像素）
    tag,           # 文字（str）
    fontStyle      # 文字字体
)  
```
由于添加文字时是通过左上角坐标添加，如果要实现居中或者靠右，就需要知道文字长度

本函数主要是通过计算文字在图片上的长度实现文字的居中或者靠右的功能

需要居中的x坐标-文字长度/2 即可实现文字居中的效果

### 4 形状的添加

```python
box_list.append([
    
    (364+478*i, 816),           # 矩形的左上角坐标
    (499+478*i, 849),           # 矩形的右下角坐标
    pr_info(avg_pr)[1]          # 填充矩形的颜色

])
```

例如我们需要图片中需要添加一个矩形来表示用户的pr，就需要通过上面的方式往box_list写入数据

通过这个功能也可以实现柱状图的效果

### 5 成就图片的叠加

```python
i = 1                           # 计数用
x = i % 4
y = int(i / 4)
achievement_png_path = os.path.join(file_path, 'png', 'achievement', '{}.png'.format(index[0]))  # 成就图片的路径
achievement_png = cv2.imread(achievement_png_path, cv2.IMREAD_UNCHANGED)                         # 读取图片
achievement_png = cv2.resize(achievement_png, None, fx=1.4, fy=1.4)                              # 图片大小resize
x1 = 2991+200*x                                                                 # 叠加图片的左上角x坐标
y1 = 473+140*y                                                                  # 叠加图片的左上角y坐标
x2 = x1 + achievement_png.shape[1]
y2 = y1 + achievement_png.shape[0]
res_img = merge_img(res_img, achievement_png, y1, y2, x1, x2)                   # 将成就图片叠加到背景图片上
del achievement_png                                                             # 释放资源
text_list.append([(x1+100, y1+85), 'x'+str(index[1]), (0, 0, 0), 1, 35])        # 添加成就数量的文字
```
通过cv2模块实现在不丢失alpha通道的情况下，实现图片叠加


### 6 图片最后处理

```python
if (isinstance(res_img, np.ndarray)):                   # 将图片类型转换为pil能处理的mat类型
    res_img = Image.fromarray(
        cv2.cvtColor(res_img, cv2.COLOR_BGR2RGB))
res_img = add_box(box_list, res_img)                    # 在图片上添加形状
res_img = add_text(text_list, res_img)                  # 在图片上添加文字
res_img = res_img.resize((2640, 1376))                  # 缩小图片，方便发送
return res_img                                          # 返回图片
```

这步通过pil模块实现往图片上批量添加文字和形状

之所以在最后一步统一添加是因为前面图片叠加是通过cv2模块实现的，而把图片从cv2可读取的类型转换为pil可读取的类型是一个比较耗时的操作，这样可以节约时间

