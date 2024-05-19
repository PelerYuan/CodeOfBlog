---
title: RuoZhiBa performed the best as datasets to AI?
author: Peler
top: false
cover: false
toc: true
mathjax: false
date: 2024-04-06 15:27:46
img: https://ice.frostsky.com/2024/04/06/011a8666b8caf48f569a808d1fc294fd.png
coverImg:
password:
summary:
keywords:
tags:
    - daily life
    - GitHub Projects
    - AI
    - ChatGPT
categories: news
---
I saw the news in the morning and I think it is the most interesting things that I have ever heard of about AI.

Here's the paper at <https://arxiv.org/abs/2403.18058>.

Also there's a project of datasets from Rozhiba on Github: <https://github.com/Leymore/ruozhiba/tree/main>.

Let me try to make a conclusion(not very precise). People from Shenzhen Institute of Advanced Technology, Peking University, University of Science and Technology of China and other famous universities made a varity of datasets from different Chinese Internet communities. They used these datasets for AI training and finally find that the data from Rozhiba performed the best!

By the way, here's the introduction of Rozhiba, written in the paper:
![introduction of RoZhiBa](https://ice.frostsky.com/2024/04/06/fa0b537fec15fa4dd11402154bb24604.png)

They tried two models and Rozhiba always got the highest score(except Math):
![](https://ice.frostsky.com/2024/04/06/72994d37ce9b20fa650f1b4f1e5b298f.png)

They gave the explanation:
![](https://ice.frostsky.com/2024/04/06/d6971918a48d822040d9179ebddd44c2.png)

## What I thought
After reading the paper and thinking for a while, I would like to say that it's not a surprise.

The way that people evalutate the dataset is just to ask ChatGPT to answer the question, and manually do some modification to make sure that the answer is correct, then throw it to the training model.

Which means that, text contains jokes, logical thinkings, abstractions can benefit the model more, and that's what Rozhiba have indeed(that's why we called it Rozhiba).

But overall it's an perfect amusement, people in Ruozhiba even discussed this, and really makes me laugh(you can see the posts at <https://tieba.baidu.com/p/8964992247>):
![one of the posts from Rozhiba](https://ice.frostsky.com/2024/04/06/d641e4681b548e5a381a8d5df1d8b1ab.png)

![one of the posts from Rozhiba](https://ice.frostsky.com/2024/04/06/5263c6decf6a43e93540f04e5e440b86.png)

Especially this advertisement:
![](https://ice.frostsky.com/2024/04/06/8ad2546c174126793aebb36e0bea50d7.png)

LOL