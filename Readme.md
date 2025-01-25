## Movie
数据来自于https://grouplens.org/datasets/movielens/10m/
电影推荐数据集
```

cd movie
wget https://files.grouplens.org/datasets/movielens/ml-10m.zip

unzip -j ml-10m.zip
python movie_process.py
```

## Game
数据来自于https://cseweb.ucsd.edu/~jmcauley/datasets/amazon_v2/
亚马逊评论数据中的video game子分类

```

cd game
wget https://datarepo.eng.ucsd.edu/mcauley_group/data/amazon_v2/metaFiles2/meta_Video_Games.json.gz
wget https://datarepo.eng.ucsd.edu/mcauley_group/data/amazon_v2/categoryFilesSmall/Video_Games_5.json.gz
gzip -d Video_Games_5.json.gz
gzip -d meta_Video_Games.json.gz
python game_process.py
```

## 数据说明
game中每条数据是一个用户的推荐序列，输入是"history_movie_id"：用户看的历史电影id序列，模型预测结果为"movie_id"
movie中每条数据是一个用户的观看序列，输入是"history_item_id"：用户看的历史video id序列，模型预测结果为"item_id"
生成train.json, valid_5000.json, test_5000.json三个文件，其中train.json只需要random的sample 1024个样本进行训练，valid_5000.json是验证集, test_5000.json是测试集