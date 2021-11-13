# install and set up miniconda on CVM
## 安装conda
```bash 
sh Miniconda3-latest-Linux-x86_64.sh
```

## 更新环境变量
```bash 
source ~/.bashrc
```

## 设置清华大学源
```bash 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
conda config --set show_channel_urls yes
```

## 设置中科大源
```bash 
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/bioconda/
conda config --set show_channel_urls yes
```

## 查看镜像地址是否设置成功
```bash 
cat ~/.condarc
```

## 创建环境
```bash 
conda create -n wsweb
```

## 进入环境
```bash 
conda activate wsweb
```

## 退出环境
```bash 
conda deactivate
```

## 删除环境
```bash 
conda env remove --name wsweb
```

## 安装软件
```bash 
conda install numpy
```

## 更新软件
```bash 
conda update numpy
```

## 卸载软件
```bash 
conda uninstall numpy
```

## 查看已装软件列表
```bash 
conda list
```