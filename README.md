#### 姓名转拼音

1. 姓氏：优先匹配百家姓，百家姓匹配不到则转为微软的拼音转换
2. 名称：优先匹配redis上的多音字数据，如果没有，匹配已有数据库内的多音字数据；都没有时，转为微软的拼音转换
3. 名称部分的优先命中规则是根据数据库内的数据优先匹配，可以通过插入数据库数据或者调用addPinyin()方法来加入优先匹配数据
4. 热更新方案为插入新的数据后清除redis，这样在下一次调用时可以直接从数据库读取最新的存放到redis中