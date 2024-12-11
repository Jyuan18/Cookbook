# conda

```python
# 环境-新建、删除、罗列、激活、退出
conda create -n ENV_NAME python=3.10.x
conda env remove -n ENV_NAME --all
conda env list
conda activate ENV_NAME
conda deactivate

# 包-安装、删除、罗列
conda install PACKAGE_NAME
conda remove PACKAGE_NAME
conda list
conda update [-n ENV_NAME] [PACKAGE_NAME] [--all]

# 版本
conda --version
python --version

# 镜像源-添加、删除、展示、查看
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --add channles htts://mirrors.ustc.edu.cn/anaconda/pkgs/free/
conda config --remove channels "https://xxx"
conda config --set show_channel_urls yes
conda config --show-sources

```



