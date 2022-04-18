# Actional-Structural Graph Convolutional Networks for Skeleton-based Action Recognition
![AS-GCN IMAGE](https://github.com/limaosen0/AS-GCN/raw/master/img/pipeline.png)
- AS-GCN: Actional-Structural Graph Convolutional Network

## definition
> Action recognition with skeleton data has recently attracted much attention in computer vision. 
>Previous studies are mostly based on fixed skeleton graphs, only capturing local physical dependencies among joints, 
>which may miss implicit joint correlations. To capture richer dependencies, 
>we introduce an encoder-decoder structure, called A-link inference module, 
>to capture action-specific latent dependencies, i.e. actional links, directly from actions. 
>We also extend the existing skeleton graphs to represent higher-order dependencies, 
>i.e. structural links. Combing the two types of links into a generalized skeleton graph, 
>we further propose the actional-structural graph convolution network (AS-GCN), 
>which stacks actional-structural graph convolution and temporal convolution as a basic building block, 
>to learn both spatial and temporal features for action recognition. 
>A future pose prediction head is added in parallel to the recognition head to help capture more detailed action patterns through self-supervision. 
>We validate AS-GCN in action recognition using two skeleton data sets, NTU-RGB+D and Kinetics. 
>The proposed AS-GCN achieves consistently large improvement compared to the state-of-the-art methods. 
>As a side product, AS-GCN also shows promising results for future pose prediction.

## Abstract
- ST-GCN에 A-link 구조를 더해 관절간의 관계성을 향상시킴.
- A-link는 인코더-디코더 구조로 구성되는데, 이 구조를 통해 인근에 연결되어 있는 관절간의 관계성 뿐만 아니라 멀리 떨어져있는 관절관의 관계성도 찾아낼 수 있다.
- S-link와 A-link를 이용

## ST-GCN
- Spatial Temporal Graph Convolutional Networks
- 한 프레임의 skeleton을 계층적 구조에 따라 그래프를 연결하는 것이 아니라, 공간상, 시간상에서 모두 연결하여 두 특징을 모두 학습할 수 있다.
- 프레임 입력 -> 시간에 따른 공간적 연산 -> 시간축에 대한 GCN 연산
- convolution과정: 관절마다 시간축에 따라 1d 컨볼루션을 하는데 이 때 vertex matrix에서는 (joint x joint x time)에서 (1 x 1 x time graph) convolution이 이루어짐.
- 단점: 관절의 관계성을 로컬영역에서 밖에 찾지 못한다 -> 주어진 최대 distance에 따라 연결되어진 관절 간의 관계성만 찾을 수 있다.
-> 즉, 시간축에서 멀리 떨어진 위치(관절)과의 관계성을 추가로 찾지 않고 이웃한 시간과의 연산만 하게 된다. 이 때 다른 관절과의 관계성도 제외가 된다.
- 위 단점을 보안 => AS-GCN

## Tasks
- action recognition
- pose prediction
- skeleton based action recognition
- temporal action localization

## DataSets
- Kinetics
- NTU RGB+D

## 알고리즘 과정
1. 동영상으로부터 skeleton을 추출한다.
2. 미리 학습시킨 인코더-ㄷ코더 구조를 통해 A-link를 추출한다.
3. skeleton으로부터 S-link를 추출한다.
4. 총 9개의 AS-GCN 모듈을 통해 feature를 추출한다
5. pooling과 softmax 함수를 이용하여 행동을 분류한다.

# 참고자료 & 논문 등 출처
[official code](https://github.com/limaosen0/AS-GCN)
[community code](https://paperswithcode.com/paper/actional-structural-graph-convolutional)
[Actional-Structural Graph Convolutional Networks for Skeleton-based Action Recognition 2019](https://arxiv.org/pdf/1904.12659.pdf)
[참고 블로그](https://reading-cv-paper.tistory.com/entry/AAAI-2018Spatial-Temporal-Graph-Convolutional-Networks-for-Skeleton-Based-Action-Recognition)
