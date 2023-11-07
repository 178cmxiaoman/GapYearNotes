# 机器学习基本知识点
## 什么是mAP?

[参考博客](https://blog.csdn.net/shuiyixin/article/details/86349643?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169841244316800225526092%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=169841244316800225526092&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-2-86349643-null-null.142^v96^pc_search_result_base4&utm_term=mAP&spm=1018.2226.3001.4187)

1. True positives(TP):  被正确地划分为正例的个数，即实际为正例且被分类器划分为正例的实例数（样本数）；

2. False positives(FP): 被错误地划分为正例的个数，即实际为负例但被分类器划分为正例的实例数；

3. False negatives(FN):被错误地划分为负例的个数，即实际为正例但被分类器划分为负例的实例数；

4. True negatives(TN): 被正确地划分为负例的个数，即实际为负例且被分类器划分为负例的实例数。

P 代表 precision，即精确率，精确率表示预测样本中实际正样本数占所有正样本数的比例，计算公式为：

```
precision = TP/（TP+FP）
```
R 代表 recall ，即召回率，召回率表示预测样本中实际正样本数占所有预测的样本的比例，计算公式为：  
```
Recall = TP/(TP+FN)
```
一般来说，**召回率越高，准确率越低**。

**mAP**(Mean Average Precision)即均值平均精度。作为 object dection 中衡量检测精度的指标。计算公式为：
```
mAP = 所有类别的平均精度求和除以所有类别。
```

















