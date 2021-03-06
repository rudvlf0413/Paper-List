# Deep Learning Papers


### Vision & Video & GAN

* [Generative Adversarial Nets](https://arxiv.org/abs/1406.2661)
    - 첫 GAN 모델 제안
    - Minimax game


* [UNSUPERVISED REPRESENTATION LEARNING WITH DEEP CONVOLUTIONAL GENERATIVE ADVERSARIAL NETWORKS](https://arxiv.org/abs/1511.06434)
    - 기존 GAN 모델을 더 안정적으로 학습할 수 있는 방법(technique) 제시   


* [Conditional Image Generation with PixelCNN Decoders](https://arxiv.org/abs/1606.05328)

    - Generative Model
    - PixelRNN에 비해 더 빠르게 학습 가능
    - Gated convolutional layers, residual connections
    - latent vector h를 추가함으로서 conditional Generative model로 사용 가능


* [Pixel Recurrent Neural Networks](https://arxiv.org/abs/1601.06759)

    - Diagonal BiLSTM 기반 Image Generative model
    - Residual blocks, Residual connections


* [Learning to Discover Cross-Domain Relations with Generative Adversarial Networks](https://arxiv.org/abs/1703.05192)

    - 기존 GAN 모델에 Cross-domain relation을 적용할 수 있도록 새로운 GAN 모델 설계 (DiscoGAN)
    - GAN with reconstruction loss에 비해 mode collapse 문제를 좀 더 해결할 수 있음


* [Faster R-CNNL Towards Real-Time Object Detection with Region Proposal Networks](https://arxiv.org/abs/1506.01497)

    - 1x1 convolution filter
    - box regression layer, box-classification layer


* [Recurrent Models of Visual Attention](https://papers.nips.cc/paper/5542-recurrent-models-of-visual-attention.pdf)

    - 전체 사진을 보지 말고 매 스텝마다 일부 패치를 보고 다음 스텝에서 해당 패치에서 어느 위치의 패치 뽑아서 인식할지를 학습
    - controller는 RNN, Reinforcement learning으로 학습


* [On the Effects of Batch and Weight Normalization in Generative Adversarial Networks](https://arxiv.org/pdf/1704.03971.pdf)

    - Batch normalization에서 나타나는 mode collapse를 방지하기 위해 weight normalization 제안
    - Translated ReLU, gradient 기반의 mean squared Euclidean distance evaluation 제안
    - 기존 DCGAN보다 좋은 성능, 다만 새로운 GAN들과의 비교 부족이 아쉬움
* [Self-supervised learning of visual features through embedding images into text topic spaces](https://arxiv.org/abs/1705.08631)

    - 위키피디아에 있는 문서-이미지 쌍을 데이터셋으로 하여, 문서 집합을 토픽모델링(LDA)를 통해 토픽 분포를 추출하고, 이미지를 CNN 모델을 통해 해당 문서의 토픽 분포를 예측하도록 함
    - 각 이미지가 유사한 토픽끼리 클러스터링 됨
    - 이미지 검색 등에 활용 가능성
* [Reffering Relationships](https://arxiv.org/abs/1803.10362)

    - 이미지와 이미지 안에 있는 관계 (e.g. Person, Kicking, Ball)를 통해 해당하는 Subject와 Object를 찾아내는 태스크
    - 해당하는 문제는 Subject, Object 크기에 따라 난이도가 다르며, 두 객체와 두 객체의 관계(predicate)에 따라 봐야하는 부분이 달라진다.
    - 이 문제를 위해 각 객체와 객체의 관계에 따라 attention이 변화할 수 있도록 모델링함 (Symmetric stacked attention shifting model) 
* [Text-Adaptive Generative Adversarial Networks: Manipulating Images with Natural Language](https://arxiv.org/abs/1810.11919)

    * 이미지와 변환하려는 text를 인풋으로 넣어서 변환하려는 text에 맞게 이미지를 변환함
    * Attention과 Word-level로 descriminator loss를 발생시켜, 특정 단어들에 대한 특징을 이미지에 잘 변환되도록 함



### Word/Sentence Embedding

* [Query Expansion with Locally-Trained Word Embeddings](http://www.aclweb.org/anthology/P16-1035)

    - Local word Embedding 개념을 도입


* [Cross-lingual Models of Word Embeddings: An Empirical Comparison](http://www.aclweb.org/anthology/P16-1157)

    - Cross lingual word embedding 4가지 모델(BiSkip, BiCVM, BiCCA, BiVCD)를 실험적으로 비교함


* [Embeddings for Word Sense Disambiguation: An Evaluation Study](http://www.aclweb.org/anthology/P16-1085)

    - Word Sense Disambiguation를 해결하기 위해 몇가지 기법들을 제시
    - 이 중 Fractional decay가 효과적 (이웃 단어들의 거리를 고려한 가중 평균)


* [On the Role of Seed Lexicons in Learning Bilingual Word Embeddings](http://www.aclweb.org/anthology/P16-1024)

    - 기본적인 seed lexicon들을 가지고 bilingual에 대해 어떻게 학습을 할지 실험 비교


* [Distributed Representations of Words and Phrases and their Compositionality](http://web2.cs.columbia.edu/~blei/seminar/2016_discrete_data/readings/MikolovSutskeverChenCorradoDean2013.pdf)

    - Skip-gram 모델 첫 제안


* [Skip-Thought Vectors](https://arxiv.org/abs/1506.06726)

    - Sentence를 embedding 하는 방법 제안
    - 주어진 input sentence를 RNN Encoder-Decoder에 넣어 전/후 sentence를 예측하도록 학습


* [Swivel: Improving Embeddings by Noticing Whats Missing](https://arxiv.org/abs/1602.02215)

    - 전체 PMI를 이용하여 word embedding 학습
    - PMI Matrix가 매우 크므로 분산 처리
    - Matrix를 block으로 나눠서 분산 처리 함 


* [Supervised Word Mover's Distance](https://papers.nips.cc/paper/6139-supervised-word-movers-distance.pdf)

    - 두 document의 거리를 bag of words 대신 각 단어 사이 거리를 이용해서 계산
    - 기존 Word Mover's Distance를 업그레이드한 버전, time complexity 개선
    - 비슷하게 Wasserstein distance가 있음
    - Neighbor Component Analysis + Leave-one-out classification으로 학습


* [A simple but though-to-beat baseline for sentence embeddings](https://arxiv.org/abs/1707.03264)

    - 이미 학습되어 있는 word embedding vector들을 조합해서 sentence embedding 생성
    - Random walk를 이용하여 tf-idf와 같은 단어의 weight와 embedding vector의 조합으로 sentence embedding 생성
    - 전체 문장의 embedding vector에 대해서 첫번째 eigenvector(통사적으로 주로 쓰이는 문장 벡터)를 제거
    - Unsupervised로 문장 임베딩 벡터를 계산하는데에 의의, 높은 성능

* [Topical word embeddings](http://nlp.csai.tsinghua.edu.cn/~lzy/publications/aaai2015_twe.pdf)

    - Topic modeling을 통해 각 단어의 토픽 결정
    - skip-gram model에 word embedding과 해당 단어에 해당하는 topic의 embedding vector 결합
    - polysemy 문제 해결

* [Unsupervised Word and Dependency Path Embeddings for Aspect Term Extraction](https://arxiv.org/abs/1605.07843)

    - Word embedding과 dependency path를 graph embedding처럼 결합
    - 각 word embedding w1, w2와 dependency path r에 대해 w1-w2과 r과의 거리를 가깝도록 함
    - 학습된 embedding feature를 가지고 CRF를 학습하고 Aspect term extraction 수행


### Natural Language Processing (Language Model, QA, Sentiment Analysis, etc.)

* [Sequence to Sequence Learning with Neural Netowrks](https://papers.nips.cc/paper/5346-sequence-to-sequence-learning-with-neural-networks.pdf)

    - Encoder Decoder 형식의 Sequence to sequence model 제안
    - Encoder의 마지막 hidden vector를 sentence를 embedding할 수 있음을 시각화함


* [Learning Phrase Representations using RNN Encoder-Decoder for Statistical Machine Neural Traslation](https://arxiv.org/abs/1406.1078)

    - GRU 모델 제안, GRU 기반의 sequence to sequence 모델


* [Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473)

    - 첫 Attention Mechanism 제안
    - Attention을 통해 학습이 잘되고 더 긴 문장에 대해서도 효과적


* [SeqGAN: Sequence Generative Adversarial Nets with Policy Gradient](https://arxiv.org/abs/1609.05473)

    - Generative Adversarial Networks를 sequence 모델에 도입한 거의 첫 사례
    - Policy gradient와 MC sampling을 사용하여 학습


* [Neural Networks For Negation Scope Detection](http://www.aclweb.org/anthology/P16-1047)

    - 부정어의 범위를 찾기 위해 뉴럴넷 사용


* [Event Detection and Domain Adaptation with Convolutional Neural Networks](http://anthology.aclweb.org/P/P15/P15-2060.pdf)

    - Word Embedding과 CNN을 사용하여 text에서 event detection 수행


* [Using Sentence-Level LSTM Language Models for Script Inference](https://arxiv.org/abs/1604.02993)

    - Rare Word에 대한 embedding을 common word의 조합으로 대체
    - ZRegression으로 softmax를 대체하여 효율적으로 처리


* [Convolutional Neural Networks for Sentence Classification](http://www.aclweb.org/anthology/D14-1181)

    - word 단위로 embedding한 벡터들의 sequence를 CNN과 max pooling을 통해 text classification 수행
    - 기존 RNN에 비해 classification accuracy도 좋고 학습 속도도 빠름


* [Neural Summarization by Extracting Sentence and Words](https://arxiv.org/abs/1603.07252)

    - Encode part에서 recurrent convolutional document reader 사용
    - word extraction에서는 neural attention 모델 사용


* [Sentence Compression by Deletion with LSTMs](https://static.googleusercontent.com/media/research.google.com/ko//pubs/archive/43852.pdf)

    - LSTM 모델을 이용한 sentence compression(summarization)


* [Learning to Compose Neural Networks for Question Answering](https://arxiv.org/abs/1601.01705)


* [End-To-End Memory Networks](https://arxiv.org/abs/1503.08895)

    - Memory network(multiple layer)를 도입하여 input sequences와 question을 비교하며 어느 부분을 단계적으로 주목해야할지 계산
    - Question Answering에서 유용


* [Generating Factoid Questions With Recurrent Neural Networks: The 30M Factoid Question-Answer Corpus](http://www.aclweb.org/anthology/P16-1056)

    - GRU 모델을 이용, Freebase 데이터셋을 기초로 하여 QA corpus를 생성함


* [Ask Me Anything: Dynamic Memory Neural Networks for Natural Language Processing](https://arxiv.org/abs/1506.07285)

    - GRU, Attention model을 이용한 Dynamic Memory Networks


* [Abstractive Sentence Summarization with Attentive Recurrent Neural Networks](http://nlp.seas.harvard.edu/papers/naacl16_summary.pdf)

    - RNN 모델에 Attention mechanism을 적용하여 sentence summarization을 수행
    - 흥미로운 점은 Elman RNN(기존 RNN)이 LSTM보다 결과가 좋음 - overfitting일수도...


* [Text Understanding with the Attention Sum Reader Network](https://arxiv.org/abs/1603.01547)

    - cloze test (빈칸추론)을 수행하기 위해 bidirectional RNN 사용
    - 여기에 attention sum reader 모델(Pointer network에 영감) 소개


* [Towards AI-Complete Question Answering: A Set of Prerequesite Toy Tasks](https://arxiv.org/abs/1502.05698)

    - bAbI를 생성
    - 기존 모델 - LSTM, SVM, MemNN 등을 실험을 통해 비교


* [Adversarial Neural Machine Translation](https://arxiv.org/abs/1704.06933)

    - NMT 작업에 Adversarial technique 도입
    - discriminant에서는 input과 output을 concatenate한 tensor를 convolution을 통해 진짜/가짜 판별
    - generate에서는 가짜 sequence 생성
    - 학습은 MLE와 policy gradient를 번갈아가며 학습, 기존 MLE 방식보다 BLEU score 개선


* [Convolutional Sequence to Sequence Learning](https://arxiv.org/abs/1705.03122)

    - 기존 RNN 기반의 sequence to sequence를 CNN으로 대체하려는 시도
    - Position embedding, residual connection, attention
    - GLU (Gated Linear Unit)
    - Initialization weight를 수학적으로 유도


* [Quasi-Recurrent Neural Networks](https://arxiv.org/abs/1611.01576)

    - RNN 방법에 CNN 방법을 접목 시킴
    - 먼저 전체 time step에 대해 convolution을 하고 time step에 따라 liear multiplication을 없애 속도를 빨리 함
    - 해당 모델에 따른 Attention과 sequence to sequence 방법도 제시
    - 기존 LSTM에 비해 속도도 빠르면서 성능도 개선, 더 긴 sequence에 대해서 학습 가능성

* [A simple neural network module for relational reasoning](https://deepmind.com/blog/neural-approach-relational-reasoning/)

    - o_i, o_j에 대해 g(o_i, o_j)가 한 pair의 추론된 relation
    - 이것을 전체 pair에 대해서 sum을 한 뒤 f를 걸쳐 전체를 reasoning하는 모듈로 설계
    - CLEVER Dataset에 대해 매우 높은 정확도 ( > human)


* [Unsupervised Neural Machine Translation](https://arxiv.org/abs/1710.11041)

    - 기존 attention 기반 encoder-decoder에서, encoder는 sharing하고 decoder는 두 언어로 둬서 paired data가 아닌 monolingual data들을 가지고 학습
    - denoising: encoder에 input sentence를 이웃끼리 순서를 섞어서 noise를 주고 decoder에서 원래 순서를 추론하도록 학습
    - on-the-fly backtranslation: L1(L1_i)을 인풋으로 하여 나온 두 아웃풋(L1_d, L2_d)에 대해
      L2_d를 psudo pair sentence로 하여 다시 encoder에 놓고 번역후(L1) L1_i와 L1을 supervised l
earning으로 학습함
    - 이 모델을 기반으로 Semi-supervised로 했을 때 성능이 더 오름


* [Detect Rumor and Stance Jointly by Neural Multi-task Learning](https://dl.acm.org/citation.cfm?id=3188729)
  
    - Rumor detection과 stance detection을 동시에 하면서 학습함
    - GRU Layer 하나를 두 태스크가 공유함
    - 특이한건 각 문장에 대한 벡터 인풋으로 tf-idf vector를 인풋으로 함


* [Machine Comprehension by Text-to-Text Neural Question Generation](https://arxiv.org/abs/1705.02012)

    - Question generation task를 위한 neural network 모델 제안
    - Pointer network + attention 기반의 sequence to sequence 모델
    - maximum likelihood training + 리워드를 통한 policy gradient 학습
    - 기존 학습된 모델들을 통해 얼마나 질문 같은지에 대한 reward와 얼마나 문장같은지에 대한 reward를 추정함
* [Interactive Attention Networks for Aspect-Level Sentiment Classification](https://www.ijcai.org/proceedings/2017/0568.pdf)
    - 기존의 sentiment analysis에서 더 나아가 context sentence에서 target에 대한 감정을 분석하도록 함
    - 예시) context - 이 영화는 재밌지만 배우 연기는 별로다, target - 배우 => 부정적으로 예측
    - target과 context가 서로 interaction을 통해 attention을 구하도록 함
* [Recurrent Attention Network on Memory for Aspect Sentiment Analysis](https://www.cs.cmu.edu/~lbing/pub/emnlp17_aspect_sentiment.pdf)
    - Interactive Attention Networks for Aspect-Level Sentiment Classification 논문과 비슷하게 sentence에서 target word에 대한 감정 분석을 함, 단 target word는 문장안에 무조건 있다는 가정
    - bidirectional lstm에서 나온 hidden state vector에다가 target word와의 거리를 가중치를 줌
    - 여기에 attention weight을 GRU를 통해 step에 따라 변화하도록 계산함
* [Hierarchical Attention Networks for Document Classification](http://tinyurl.com/yayalcef)

    - Document classification에 word-level, sentence-level의 attention 적용
    - Attention에 쓰이는 content vector 또한 trainable vector
* [Exploiting Coarse-toFine Task Transfer for Aspect-level Sentiment Classification](https://arxiv.org/abs/1811.10999)

    * Sentiment analysis 관련 데이터셋에 대해 한 도메인은 데이터셋 크기가 메우 작은 경우, 데이터셋 크기가 큰 도메인을 활용해서 transfer learning을 적용하여 학습함
    * 또한 Aspect sentiment analysis로 주어진 문장으로부터 주어진 카테고리에 대한 감정 스코어를 계산함
    * 하지만 도메인이 다른 경우 단어의 감정 스코어나 중요도가 다르기 때문에 이를 맞춰주기 위한 Attention 모듈들과 Loss들을 소개함



### Speech & Sound

* [Towards End-to-End Speech Recognition with Recurrent Neural Networks](http://mickey-luke.de/ASR2.pdf)
  
    - 음성을 텍스트로 인식하는 task
    - Bidirectional RNN 사용
    - 음성 길이와 텍스트 길이가 다르므로 학습을 위해 Connectionist Temporal Classification(CTC) 방법 제시


* [WaveNet: A Generative Model For Raw Audio](https://arxiv.org/abs/1609.03499)

    - Directed Casual Convolutions 모델 제안
    - Gated Activation units, residual, skip connections 사용
    - TTS(Text to Speech)에도 적용



### Machine Learning(Deep learning) theory & Model

* [Training Products of Experts by Minimizing Constrative Divergence](http://www.cs.toronto.edu/~fritz/absps/tr00-004.pdf)

    - RBM을 효율적으로 학습하기 위해 Gibbs sampling과 Constrative Divergence 방법 도입?


* [A fast learning algorithm for deep belief nets](https://www.cs.toronto.edu/~hinton/absps/fastnc.pdf)

    - Generative model인 DBN을 효율적으로 학습하기 위한 방법 제시?


* [Maxout networks](http://proceedings.mlr.press/v28/goodfellow13.pdf)

    - 새로운 형태의 activation function(maxout) 제시


* [SqueezeNet: AlexNet-level accuracy with 50x fewer parameters and <0.5MB model size](https://arxiv.org/abs/1602.07360)

    - 모델의 크기를 줄이면서 성능은 거의 유지시킴
    - 1 by 1 filter 도입


* [Neural Architecture Search with Reinforcement Learning](https://research.google.com/pubs/pub45826.html)

    - RNN Controller가 뉴럴넷의 hyper parameter를 설정, 해당 뉴럴넷을 학습
    - Child net의 에러를 리워드로 하여 RL을 통해 학습(Policy gradient)
    - 분산 처리 학습 (Asynchronous updates)


* [Learning Deep Nearest Neighbor Representations Using Differentiable Boundary Trees](https://arxiv.org/abs/1702.08833)

    - Boundary tree를 확률 기반, 미분 가능하게 모델을 설계하고 이를 뉴럴넷으로 학습
    - 이를 통해 더 좋은 representation을 뽑아낼 수 있도록 하고
    - tsne에서 시각화 했을 때 그룹간 겹치는 현상을 방지함


* [Deep Forest: Towards an Alternative to Deep Neural Netowrks](https://arxiv.org/abs/1702.08835)

    - 기존 forest를 DNN처럼 Cascade(stacking)을 통해 더 좋은 성능을 낼 수 있도록 함
    - 딥러닝에 비해 Small size dataset에 대해 좋은 효과를 발휘함


* [Locally Optimized Product Quantization for Approximate Nearest Neighbor Search](http://image.ntua.gr/iva/files/lopq.pdf)

    - large size dataset에서 주어진 vector와 가장 가까운 데이터를 찾는 것은 매우 시간이 걸림
    - 따라서 k-means와 같이 quantization 방법을 사용
    - 하지만 k-means도 계산할 때 memory, time이 매우 많이 듦
    - 이를 해결하기 위해 정확도 손실도 적으면서 속도도 빠른 LOPQ(Locally Optimized Product Quantization) 방법 제안


* [Hybrid computing using a neural network with dynamic external memory](https://deepmind.com/blog/differentiable-neural-computers/)

    - Differentiable neural computer
    - 외부 메모리에 저장하는 것처럼 거대한 메모리(matrix)에 읽고 쓰기 하는 작업을 differentiable function으로 정의
    - 읽고 쓰기 등의 작업은 controller에서 작업 통제
    - 메모리를 통해 더 긴 sequence에 대해서도 우수한 성능을 보임


* [Self-Normalizing Neural Networks](https://arxiv.org/abs/1706.02515)

    - 기존 ELU(Exponentional Linear Unit)에서 mean, variance가 (0, 1)로 되도록 alpha 설정
    - 이에 따라 dropout도 새로 설계


* [Forward Thinking: Building and Training Neural Networks One Layer at a Time](https://arxiv.org/abs/1706.02480)
  
    - 한 레이어를 충분히 학습하면 그 레이어는 더이상 학습을 하지 않도록 하고 그 위에 추가 레이어를 쌓는 방법
    - 학습을 할 때는 이전 layer에는 더이상 back propagation을 하지 않으므로 학습 속도가 빨라짐
    - MNIST에만 실험했다는 한계

* [Factorized Variational Autoencoders for Modeling Audience Reactions to Movies](https://www.cs.sfu.ca/~mori/research/papers/deng-cvpr17.pdf)

    - Tensor Factorization과 Autoencoder 결합
    - 각 사람과 시간을 결합한 latent vector 생성, decoder에서 사람 얼굴(landmark) generation

* [Efficient Neural Architecture Search via Parameter Sharing](https://arxiv.org/abs/1802.03268)

    - 기존 neural architecture search에 비해 성능을 높이고 학습 속도를 대폭 높임
    - single directed acyclic graph 이용
    - parameter sharing을 통해 child network의 학습 속도를 대폭 높임
    - 여러가지 technique 추가

* [Attention is All you need](https://arxiv.org/abs/1706.03762)
    - Query, Key, Value를 통해 lstm의 순차적인 embedding 방식에서 벗어나 한번에 encoding해서 효율적으로 계산함
    - Multi hop 방식과 Multi channel 방식을 사용
    - 순서 정보를 위해 Positional encoding을 사용하되, 각 차원별로 다른 주기의 sinusoid 함수를 사용

* [Adversarial Network Embedding](https://arxiv.org/abs/1711.07838)
    - 네트워크에 있는 각 노드들을 임베딩함
    - Deep walk 기반으로 generator를 통해 low dimensional vector 생성,
    - Discriminator를 통해 prior distribution으로 임베딩 되도록 regularization 적용
