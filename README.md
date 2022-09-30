# OCT


---

## WEEK1

### 1. Minutes of the meeting

- enface图, GCC厚度图, 厚度图, 扇形图
- 使用OpenCV将图像拉伸
- 了解PyQt5
- 了解python-matplotlib
- 了解ctypes, pybind11 python将c++和python联通

### 2. TO DO List

- 搭建环境 √
- pybind11，用python调用c++ √
参考本人博客:`https://blog.csdn.net/qq_43369406/article/details/127002024`
- PyQt学习, Qt复现 √
参考本人博客:`https://blog.csdn.net/qq_43369406/article/details/127014248`
- VSCode使用 √
- 图像分割了解
- 运行otc_read.py, oct_seg.py √
- OpenCV
- 三种图片复现 

### 3. Question and answer 

#### Q1. .DAT文件乱码

#### Q2. 三种图像如何生成

#### Q3. VSCode中python解释器使用

1. 文件注释删除

通过取消"koroFileHeader"实现

2. .py脚本分段运行

Jupyter Notebook

`#%%`

#### Q4. Qt5 mac搭建

#### Q5. .dll / .pyd / .so 是什么
1. dll
windows下的动态链接库。
2. pyd
pyd一般是python外的其他语言如C/C++编写的python扩展模块，即python的一个动态链接库，与dll文件相当。在linux系统中一般为.so文件。
1. so
so文件是Linux下的程序函数库, 即编译好的可以供其他程序使用的代码和数据。即Linux下的动态链接库。关于动态链接库, 我们需要注意的是动态链接库是不能单独运行的, 他需要与.c .h文件放在一起才可以运行。


#### Q6. C++和python搜索头文件方式

1. C++查找头文件方式
C++搜索文件分为两种，分别是在`<iostream>`和`"stdio.h"`中寻找。
其中第一种的搜索顺序是：在环境变量中搜索。第二种的搜索顺序是是：先搜索当前路径；当前路径中未找到，再在环境变量中搜索。
2. python查找模块方式
python查找模块的顺序为: **当前包 -> 内置函数 -> sys.path(环境变量)**
其中内置函数指的是如os等系统自带的包, 存在于python36/python.zip, python36/lib, python/lib/site-packages三个包中。sys.path在import sys包中, 内置函数的3个包往往都可以在sys.path中查看到。查看方法如下：
```python
import sys
print(sys.path) # 查看系统路径, 是list数据形式
sys.path.append("/Users/yingmuzhi/anaconda3/envs/conda_OCT/lib/python3.8/site-packages/pybind11/include")   # 增加系统变量
```
补充一下mac的环境变量, 常用的有zsh和bash, 其中zsh的环境变量在`~/.zshrc`, 而bash的环境在`~/.bash_profile`。在terminal中更bash系统环境如下, 打开terminal
```bash
#!bash
echo $PATH  # 输出环境变量
vim ~/.bash_profile # 使用vim编辑器查看环境变量, 其中.bash_profile中的 . 表示该文件为隐藏文件

# --- 进入.bash_profile
export MY_DIY_PYTHON_PATH="$PATH:/Users/yingmuzhi/anaconda3/envs/conda_OCT/lib/python3.8/site-packages" # 其中MY_DIY_PYTHON_PATH是我们的变量名, $PATH是先前设置的路径, :冒号表分割符, /Users...为我们要增加的环境变量路径
```
#### Q7. CMake的使用

