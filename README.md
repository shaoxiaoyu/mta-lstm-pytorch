# MTA-LSTM-PyTorch

This is a PyTorch implementation of the paper [Topic-to-Essay Generation with Neural Networks](http://ir.hit.edu.cn/~xcfeng/xiaocheng%20Feng's%20Homepage_files/final-topic-essay-generation.pdf) of IJCAI2018.

The original implementation which was written in TensorFlow can be found [here](https://github.com/hit-computer/MTA-LSTM), but it's no longer maintained. Therefore I choose to use PyTorch, which is more straight forward than TensorFlow in my opinion, to re-implement the work.

## Dataset

The first link are 2 datasets provided by the author of the paper, and the second link, the news dataset, is prepared by myself. Simply download the files and put them into ```data``` folder.

- [Composition and Zhihu (Chinese)](https://drive.google.com/drive/folders/1oK9i0ukV5T0QoPQkHsxa3OdhQ1dVsNnL?usp=sharing)
- [News (English)](https://drive.google.com/drive/folders/1RpBMMBvgnMPjRdQaM46pyncu__QsZBZS?usp=sharing)

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
    我的夢想是長大後成為一名科學家，為實現自己的理想努力奮鬥。我要好好學習科學文化知識，長大後成為國家的棟樑之才。我堅信，只要我們努力學習科學文化知識，長大後，我們的未來一定會更加美好。
    ```
