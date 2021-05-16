# SQLAlchemy ORM框架

## 一、安装
```bash
pip install sqlalchemy==1.4.7
pip install pymysql # 连接mysql数据库所需库
```

## 二、连接数据库
```python
from sqlalchemy import create_engine
engine = create_engine(f"mysql+pymysql://{数据库账号}:{密码}@{数据库地址}:3306/{数据库}", echo=True)
print(engine)

------打印结果------
Engine(mysql+pymysql://root:***@127.0.0.1:3306/scrapy)
```

## 三、创建会话通道
```python
from sqlalchemy.orm import sessionmaker

maker = sessionmaker(bind=engine)
session = maker()
print(session)

------打印结果----------------
<sqlalchemy.orm.session.Session object at 0x03BB4400>
```

## 四、关闭会话通道
```python
session.close_all()
```

## 五、创建数据表模型
- 创建models模块，存放模型对象
- 创建表的模型对象，要继承**declarative_base**对象
- **\_\_tablename\_\_**：数据库中表的名称
- 字段要与数据库中字段对应

```python

```
