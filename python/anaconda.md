#anaconda 环境
1. 创建虚拟环境
>conda create -n name python=3
2. 切换虚拟环境
>conda activate name
3. 查看环境
>conda env list
4. 安装第三方包
>conda install name
或
>pip install name
5. 卸载第三方包
>conda remove name
或
>pip uninstall requests
6. 查看当前环境所有已安装的包
>conda list 
7. 导出当前环境的包信息,将包信息存入yaml文件中.
>conda env export > environment.yaml
8. 当需要重新创建一个相同的虚拟环境时可以用
>conda env create -f environment.yaml
```c
activate  // 切换到base环境
activate learn // 切换到learn环境
conda create -n learn python=3  // 创建一个名为learn的环境并指定python版本为3(的最新版本)
conda env list // 列出conda管理的所有环境
conda list // 列出当前环境的所有包
conda install requests 安装requests包
conda remove requests 卸载requets包
conda remove -n learn --all // 删除learn环境及下属所有包
conda update requests 更新requests包
conda env export > environment.yaml  // 导出当前环境的包信息
conda env create -f environment.yaml  // 用配置文件创建新的虚拟环境
```