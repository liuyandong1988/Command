1. conda list 查看安装了哪些包
2. conda env list  或  conda info -e  查看当前存在哪些虚拟环境
3. conda update conda  检查更新当前conda
4. conda --version  查询conda版本
5. 更新所有库 conda update --all
6. anaconda换源： 制定清华的源：
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
有资源显示源地址：
conda config --set show_channel_urls yes



## 创建python虚拟环境

使用 ``` conda create -n your_env_name python=X.X （2.7、3.6等)```命令创建python版本为X.X、名字为your_env_name的虚拟环境。your_env_name文件可以在Anaconda安装目录envs文件下找到

1. 使用激活
   conda activate your_env_name
2. 安装python包```conda install -n your_env_name [package]``` 即可安装package到your_env_name中
3. 关闭虚拟环境
   ```conda deactivate```
4. 删除虚拟环境
   使用命令 ```conda remove -n your_env_name(虚拟环境名称) --all``` ， 即可删除
5. 删除环境中的某个包
   使用命令 ```conda remove --name your_env_name package_name```  即可


## packaget manage
pip install --index-url https://pypi.tuna.tsinghua.edu.cn/simple/ package
conda list 查看安装了哪些包

