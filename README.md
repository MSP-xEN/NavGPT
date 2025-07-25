# NavGPT
## 克隆远程git仓库到本地
  git clone https://github.com/GengzeZhou/NavGPT.git
## Data Preparation
  从[Dropbox](https://www.dropbox.com/sh/i8ng3iq5kpa68nu/AAB53bvCFY_ihYx1mkLlOB-ea?dl=1)下载R2R数据集，解压到`datasets`，注意`datasets`下第一个文件夹名称是`R2R`，`R2R`里面的才是数据集
## Installation
  1.确保下载了anaconda  
  2.创建虚拟环境并下载相应的包  
  ```python
   conda create --name NavGPT python=3.9  
   conda activate NavGPT  
   pip install -r requirements.txt
  ```
## API调用
  参考[https://chatanywhere.apifox.cn/doc-5547696](https://chatanywhere.apifox.cn/doc-5547696)  
  针对本工程，如果用openai的话在`agent.py`中添加如下代码
  ```python
   import os
   os.environ["OPENAI_API_KEY"] = "your 密钥"
   os.environ["OPENAI_API_BASE"] = "https://api.chatanywhere.tech/v1"
  ```
## 测试
  参考NavGPT的readme文件  
  比较经济的方式：  
  ```python
   cd nav_src
   python NavGPT.py --llm_model_name gpt-3.5-turbo \
    --output_dir ../datasets/R2R/exprs/gpt-3.5-turbo-test \
    --val_env_name R2R_val_unseen_instr \
    --iters 10
  ```
