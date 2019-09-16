# MTA-LSTM-PyTorch

This is a pytorch implementation of the paper [Topic-to-Essay Generation with Neural Networks](http://ir.hit.edu.cn/~xcfeng/xiaocheng%20Feng's%20Homepage_files/final-topic-essay-generation.pdf) of IJCAI2018.

## Dataset

To be added...

## Prerequisites

- Python3
- PyTorch >= 1.2.0
- Gensim

## Implementation Notes

- Full vocabs were used instead of using only 50000 common words as mentioned in the original paper.
- Adaptive softmax were adopted instead of cross entropy in order to speed up training.

## Generated Examples

- Topics: 現在 未來 夢想 科學 文化
    ```
    我 的 夢想 是 長大 後 成為 一名 科學家 ， 為 實現 自己 的 理想 努力奮鬥 。 我 要 好好學習 科學 文化 知識 ， 長大 後 成為 國家 的 棟樑之才 。 我 堅信 ， 只要 我們 努力學習 科學 文化 知識 ， 長大 後 ， 我們 的 未來 一定 會 更加 美好 。
    ```
