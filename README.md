# MTA-LSTM-PyTorch

This is a PyTorch implementation of the paper [Topic-to-Essay Generation with Neural Networks](http://ir.hit.edu.cn/~xcfeng/xiaocheng%20Feng's%20Homepage_files/final-topic-essay-generation.pdf) of IJCAI2018.

MTA-LSTM stands for Multi-Topic-Aware LSTM, ultilizing multi-topic coverage vector which learns the weight of each topic during the decoding process, and is sequentially updated. The original implementation written in TensorFlow can be found [here](https://github.com/hit-computer/MTA-LSTM), but it's out-of-date and is no longer maintained. Therefore I decided to use PyTorch, which is easier and more straight forward than TensorFlow in my opinion, to reimplement the paper.

## Dataset

The first link are 2 datasets provided by the author of the paper, and the second link, the news dataset, is prepared by myself. Simply download the files and put them into ```data``` folder.

- [Composition and Zhihu (Chinese)](https://drive.google.com/drive/folders/1oK9i0ukV5T0QoPQkHsxa3OdhQ1dVsNnL?usp=sharing)
- [News (English)](https://drive.google.com/drive/folders/1RpBMMBvgnMPjRdQaM46pyncu__QsZBZS?usp=sharing)

## Prerequisites

- Python3
- PyTorch >= 1.2.0
- Gensim

## Implementation Notes

- Full vocabs were used instead of using only 50000 common words as the paper did.
- Adaptive softmax were adopted instead of cross entropy in order to speed up training process.
- The model was trained on one 1080 ti, and it took 2 days for 100 epochs.
- Beam Search method is not parallel.

## Usage

1. Run ```data/word2vec.ipynb``` to create pretrained word embedding files.
2. Run ```mta-lstm.ipynb``` to train the model.

## Generated Examples

- Topics: 現在 未來 夢想 科學 文化
    ```
    我的夢想是長大後成為一名科學家，為實現自己的理想努力奮鬥。我要好好學習科學文化知識，長大後成為國家的棟樑之才。我堅信，只要我們努力學習科學文化知識，長大後，我們的未來一定會更加美好。
    ```
