# pagodo-modified
自动化google dork搜索工具

对[pagodo](https://github.com/opsdisk/pagodo)进行了点小修改

主要是将IP被google ban之后的睡眠时间缩小(60mins->2mins)，方便使用（起码是方便我使用）

这样配合代理池，ip被ban之后，直接手动切换节点即可继续扫描，无需等待60mins，亦可设置代理ip自动切换，每个几分钟切换一次ip。

## 一般使用

首先，pagodo.py需要一个当前所有Google dorks的列表。repo包含一个dorks/目录，其中有上次运行ghdb_scraper.py时的当前dorks。
建议在运行pagodo.py之前先运行ghdb_scraper.py以获得最新的数据
```
python ghdb_scraper.py -s -j -i
```
然后运行pagodo.py，指定相应的域名和dork列表等配置即可。
以下是一个常用的命令：
```
python3 pagodo.py -d example.con -g dorks/error_messages.dorks -l -i 12 -x 20 -p socks5h://127.0.0.1:7890 -o result.json -s result.txt
```
详细使用请参考使用文档及原项目。
