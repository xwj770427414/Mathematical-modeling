# 数据缺失值处理

## 缺失值的定义

缺失值，即存在特征或标签为空值的样本。包含空值的数据会使建模过程陷入混乱，导致不可靠输出。缺少过多的数据也将丢失大量有效信息，使数据模型难以把握数据规律。

## 缺失的原因

1. 部分信息暂时无法获取
2. 由于人为因素丢失部分信息
3. 部分对象的某个或某些属性不可用

## 缺失值的处理

### 删除法

1. **特征删除法**：当一个特征缺失“过多”的数据时，对其填充的数据可能是无价值的，因此直接将该指标删除。特征值缺失量的标准无硬性规定，正常缺失30%以上便可以删除变量。
2. **样本删除法**：当含缺失值的样本量在总数据量占比较小时，可以仅删除含缺失值的样本量。

### 插值法

1. **手动插值**：填充效果最好，产生的数据偏离最小，当在处理大规模数据时不可行。
2. **统计填充**：若缺失值为数值数据，可以计算其他对象的均值或中位数来填补缺失值。若缺失值为分类数据，可以使用众数，选择在其他对象中出现频率最高的值进行填充。
3. **热卡填充法**（就近补齐）：对于一个包含空值的对象，热卡填充法在完整数据中找到一个与它最相似的对象，然后用这个相似对象的值来进行填充。通常会找到超出一个的相似对象，在所有匹配对象中没有最好的，而是从中随机的挑选一个作为填充值，不同的问题选用不同的标准来对相似进行判定。
4. **多重插补**：思想来源于贝叶斯估计，认为待插补的值是随机的，它的值来自于已观测到的值。具体实践上通常是估计出待插补的值，然后再加上不同的噪声，形成多组可选插补值。根据某种选择依据，选取最合适的插补值。

