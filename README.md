# miyoushe_crawler_for_Genshin_Impact

## 简介
一个从米游社爬取原神相关信息的爬虫  

本项目是[ACG-Game-Q-A-LLM](https://github.com/Whale-Dolphin/ACG-Game-Q-A-LLM)项目的数据获取部分，为训练模型提供原神相关的基础数据，仅作学习交流使用，不得用于商业用途。

## 功能
目前已实现：
1. 爬取米游社原神**攻略**帖子
2. 爬取米游社原神**角色**信息
3. 爬取米游社原神**武器**信息

待实现：  
-[ ] 爬取米游社原神**圣遗物**相关信息
-[ ] ...

## 依赖项
1. 安装所需依赖
```bash
    pip install -r requirements.txt
```
2. 安装`chromedriver`  
    仅在使用`selenium`时需要安装（爬取攻略帖时）

## 使用
1. 爬取攻略帖  
    **注：攻略爬取相关代码极其混乱，亟须重构，在重构完成前不推荐使用。**
   1. 使用`get_links.py`获取攻略帖链接  
   其中`get_links_v1.py`和`get_links_v2.py`是从米游社原神攻略板块获取攻略帖链接的脚本，`get_links(V4.8_related).py`是从米游社原神V4.8合集板块获取攻略帖链接的脚本。  
   `get_links(V4.8_related).py`爬取的是所有符合筛选条件的帖子链接，并不能确定是否属于攻略帖，需要进一步筛选（或在爬取结束后筛选帖子）
    使用此脚本时需要安装`selenium`和`chromedriver`。
   2. 使用`crawler.py`爬取攻略帖内容  
   其中多线程爬虫不稳定，推荐使用单线程爬虫。  
   另外强烈推荐使用**ip代理池**，否则ip大概率会被封禁。

2. 爬取角色信息  
    **注：在爬取过程中有某些页面爬取出错，bug还未定位，出错的页面URL保存在`err_when_fetch.txt`中**
   1. 使用`get_character_links.py`爬取角色链接
   2. 使用`character_crawler.py`爬取角色信息  

3. 爬取武器信息  
    **注：在爬取过程中有某些页面爬取出错，bug还未定位，出错的页面URL保存在`err_when_fetch.txt`中** 
   1. 使用`get_weapon_links.py`爬取武器链接
   2. 使用`weapon_crawler.py`爬取武器信息

所有爬取的数据均以`json`格式保存在`data`文件夹下。

## 许可证
本项目采用 MIT 许可证。

## 联系方式
如有任何问题或建议，请通过 [GitHub](https://github.com/sundowner00) 联系我。