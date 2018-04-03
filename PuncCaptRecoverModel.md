# Punc-CaptRecoverModel  

- Baseline : 基于Ngrams语言模型的TopK-prob贪心算法：
  - 优点：对训练样本表征很好，在训练样本中出现的情况都能够正确的标注；
  - 缺点：模型泛化能力不够，不能学习长句的上下文信息，语言模型较大；
  - 训练和测试：语料 ( gutenberg语料库 ) 10million sentences; 
  - 在测试集上的精度：
- 基于字符级嵌入的深度学习模型：
  - 模型结构：
    - **CNN-layer** : conv_size = [1,2,3,4,5,6]；conv_depth = 25*[1,2,3,4,5,6]，将单词按照字符级别embedding
    - **Highway-layer** : 设置转换gate,加入可学习的门限机制，类似于LSTM，不过是在embedding位置
    - **bi-LSTM-layer** : layers = 2；hidden_size = 256
    - **CRF-layer** : 对LSTM-Softmax输出加以约束，提高精度
  - 结构图如下：
  ![image](https://github.com/PROosho/PuncCaptRecoverModel/blob/master/model_achitecture.jpg)
  - 在测试集上的精度：
    - **Capt**    : **Precision**: 0.89541 | **Recall**: 0.82175 | **F1**: 0.85700
    - **Comma**   : **Precision**: 0.75975 | **Recall**: 0.73784 | **F1**: 0.74863 
    - **Period**  : **Precision**: 0.81044 | **Recall**: 0.73879 | **F1**: 0.77296
    - **Question**: **Precision**: 0.76760 | **Recall**: 0.63362 | **F1**: 0.69420
