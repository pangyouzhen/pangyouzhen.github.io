---
title: "chatglm"
date: 2023-06-25
---

# glm

GLM: General Language Model Pretraining with Autoregressive Blank Infilli

## GLM Pretraining Framework

### Pretraining Objective

#### Autoregressive Blank Infillin

![image.png](images/ca351246-2f4f-4b5f-81ba-17dcf6fd186a.png)

总结：对句子随机抽样成2部分拼接进行自回归填充

#### Multi-Task Pretrain

### Model Architecture

#### 2D Positional Encoding

图c中 position中
1. position1 中是从原始中切分的id，比如$x_{3}$的position1位置为3
2. position2 中是从part1都是0，partB都是range

思考：为什么这么做？

### Finetuning GLM

# chatglm

## chatgpt

1. pretraining
2. reward model
3. rf

## chatglm

1. 6B参数

# 微调

## p-tuning

## lora

## qlora

# 扩展

## langchain-chatglm

![image.png](acb18e58-6417-4ebc-b163-741b7c2e5f7f.png)

# 常见问题






