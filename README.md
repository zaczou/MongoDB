# MongoDB

```python
from pymongo import MongoClient
无密码连接
connection = MongoClient()
有密码连接
conn = MongoClient("10.10.1.114:10321", username="xx", password="xx", authSource="admin")
db = connection.mydb #连接mydb数据库，没有则自动创建
test = db.test  ## 使用test集合，没有则自动创建
```
# 插入数据
```python
# 插入单条, 返回x.inserted_id
x = test.insert_one({"name":"zy", "age":25})
# 插入多条
documen=[{"name":"zy", "age":25}, {"name":zs, "age":18}]
x = test.insert_many(document)
```
# 查询数据
```python
for i in test.find({}, {"_id":0}):
	print(i)
for i in test.find({"name":"zy"}):
	print(i)
```
	
# 更新数据
```python
test.update_one({"name":"zy"}, {"$set":{"age":26}})
```

# 删除数据
```python
test.remove()
```
