---
title: "记录一次lightgbm_pmml的bug"
date: 2023-06-29T18:24:36+08:00
---

# bug信息

```
Failed to convert GBDT to PMML, 
java lang IllegalArgumentException 
   at org.jpmml.lightgbm.GBDT.encodeScheme(GBDT.java:296)
```

# 版本信息

1. lightgbm==3.2.1
1. jpmml-lightgbm==1.3.6
1. 注意在最新的jpmml-lightgbm问题不存在

# 问题原因

1. 代码 `pandasCategoryIndex != this.pandas_categorical.size()`报错
1. 核心错误 `pandasCategoryIndex` 这个计数错误
1. 错误代码如下
``` 
if (LightgbmUtil.isNone(featureInfo)){
    features.add(null)
    if(hasPandasCategories){
        pandasCategoryIndex++;
        System.out.println(featureName)
    }
}
````
1. 这个代码问题点，如果某个float类型的样本不均衡，采样的时候只采样了1种，导致没有切割点，那么生成的模型文件中 `featureInfo=None`, 那么这样会加到`pandasCategoryIndex`上，导致判断条件报错