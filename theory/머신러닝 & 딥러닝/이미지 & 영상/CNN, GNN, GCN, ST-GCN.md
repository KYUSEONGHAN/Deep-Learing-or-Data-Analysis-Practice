# Graph
![graph image](https://t1.daumcdn.net/cfile/tistory/996E34335B90DB8F20)
- Graph = Node + Edge
- 비선형(non-linear) 자료구조.
- node: data를 의미
- edge: data간의 관계를 의미, 연결하는 선(line)으로 표현
- 대부분의 알고리즘은 입력 데이터가 유클리드 공간(euclidean geometry)에 있다고 가정한다. ex) 통계 데이터나 이미와 같이 **벡터**의 형태로 표현 가능해야 한다.
- **비유클리드 공간(non-eucliden geometry)의 데이터들은 오브젝트간의 복잡한 관계나 상호의존성등을 정의할 수 있는 그래프로 표현 할 수 있다.**

### 비유클리드 공간 예시
- 쇼핑에서의 상품 추천
- 화학에서 분자 구조
- 사람들간의 관계 네트워크 
- 소셜 네트워크
- 관계형 데이터베이스

### 그래프 표현 방법
1. adjancy list (인접 리스트)
2. adjacency matrix (인접행렬) 
3. feature matrix
 
## 인접행렬이란
![adjacency matrix image](https://blog.kakaocdn.net/dn/Gdb5O/btqURuGMoog/kmiBcgGSYFtYrs4Lrjepi0/img.png)
- 그래프에서 각 정점(vertex)의 연결 관계, 즉 간선(edge)의 존재 여부를 행렬로 표현한 것.
- 그래프에서 정점이 n개일 때, 각 정점을 행과 열로 하는 n차 정사각행렬이다.

# CNN이란
![cnn image](https://t1.daumcdn.net/cfile/tistory/9913A0505ECBD00329)
- Convoluion Neural Network
- Deep Neural Network에서 이미지나 영상과 같은 데이터를 처리할 때 발생하는 문제점을 보완하는 방식 중 하나
- 이미지를 분석하기 위한 패턴을 찾을때 유용하며 이미지를 직접 학습하고 패턴을 사용해 이미지를 분류한다.
- 신경망에서 학습을 통해 자동으로 적합한 필터를 생성해주는 특징이 있다.
- 특징 추출 단계 (feature extraction)
1. convolution layer: 필터를 통해 이미지의 특징을 추출
2. polling layer: 특징을 강화시키고 이미지의 크기를 줄임
- 이미지 분류 단계 (classification)
1. flatten layer: 데이터 타입을 FC네트워크 형태로 변경. 입력데이터의 shape 변경만 수행
2. softmax layer: classification 수행
- 자율주행, 얼굴인식, 객체인식 등에서 활용

## Convoluion
![convolution image](https://miro.medium.com/max/850/1*LS6qplIzS5oRWNii2KcWcA.png)
- convolution: element wise matrix multiplication + sum  (합성곱)
- convolution 과정
1. 두 행렬을 element wise로 곱한다.
2. sum()을 한다.

## Convolution Layer
- 입력 데이터로부터 특징을 추출하는 역할을 수행
- convolution layer: filter + activation function
- filter: 특징 추출
- activation function: filter 값을 비선형 값으로 바꿔주는 활성화 함수 

# GNN이란
![GNN image](https://blogik.netlify.app/static/8f34e5f6cb240b3534cf84397f87f60e/de766/end-to-end.png)

- Graph Neural Network (그래프 신경망)
- 그래프 구조에서 사용하는 인공 신경망을 뜻한다.
- 대표적인 귀납식 embedding 방법 중 하나이다.
- graph와 정점의 속성 정보를 input으로 받는다.
- gnn에서 이웃 정점들의 정보를 집계하는 과정을 반복하여 **임베딩**을 얻는다.
- 손실함수를 정의하고 난 뒤에는 학습에 사용할 대상 정점을 결정하여 학습 데이터를 구성한다.
- 핵심은 노드 사이의 관계를 모델링하고, 그에 대한 representation를 생성
- ex) node classification, graph classification, link prediction, clustering

## GNN의 구조
1. Graph Recurrent Neural Networks
2. Graph Convolutional Neural Networks
3. Graph Pooling Operators
4. Graph Attention Mechanisms
## GNN 활용
1. 학습에 사용된 정점들의 임베딩을 얻어서 똑같이 비학습정점들에게 사용한다.
2. 학습 이후에 추가된 정점의 임베딩도 얻을 수 있다.
3. 학습된 그래프 신경망을, 새로운 그래프에 적용할 수 있다.

# GCN이란
![GCN 이미지](https://blog.kakaocdn.net/dn/z6SU7/btrcf6JaWXv/OaCqpC3CFONAnlF2BPIuRk/img.jpg)
- Graph Convolution Network (그래프 합성곱 신경망)
- 이미지에 대한 convolution을 그래프 데이터로 확장한 알고리즘
- GCN: graph convolution layers + readout + fully-connected layers 
- graph convolution layer를 통해 그래프 형태의 데이터는 행렬 형태의 데이터로 변환되므로 기존 머신러닝 알고리즘을 그대로 적용할 수 있다.
- 아래 사진 3가지로 보았을 때 GCN을 최근에도 매우 활발하게 사용하는걸 확인할 수 있다. (2022.04 기) 

![](https://velog.velcdn.com/images/cosmos/post/6941b00c-7cda-422d-9f19-a9a1f42b9e6f/image.png)

![](https://velog.velcdn.com/images/cosmos/post/d0b248de-a097-4b2d-900b-d811a4ee8219/image.png)

![](https://velog.velcdn.com/images/cosmos/post/a9b4e3e1-c013-4eb2-88fc-13813dd5d740/image.png)

# ST-GCN
![ST-GCN image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fmcha0%2FbtqxECHKZR6%2FhZtIxTUkxSP4eU6KL84CUK%2Fimg.png)
- Spatial Temporal Graph Convolutional Networks
- 단점?: 관절의 관계성을 로컬영역에서 밖에 찾지 못한다.
=> 주어진 최대 distance에 따라 연결되어진 관절 간의 관계성밖에 찾지 못한다.
- 단점 보안 ST-GCN => AS-GCN(action-structural graph convolutional networks for skeleton-based action recognition)

## ST-GCN 알고리즘 설명
1. 동영상으로부터 skeleton을 추출한다.
2. skeleton data를 그래프 형태로 만든다
3. 각각의 joint들을 노드로 만들고 각각의 노드가 이어지는 부분(공간, 시간)을 edge로 연결한다.
4. 총 9개의 ST-GCN 모듈을 통해 feature를 추출한다.
5. softmax 함수를 이용하여 행동을 분류한다.

## 행동 인식 dataset
- RGB video
- depth video
- optical flow
- skeleton data

## Skeleton Dataset
![skeleton dataset image](https://media.springernature.com/lw685/springer-static/image/art%3A10.1007%2Fs10514-017-9692-3/MediaObjects/10514_2017_9692_Fig2_HTML.gif)

- 인간 관절의 2D/3D 좌표만으로 구성된 데이터로서 인간의 동작 인식을 위해 연구되었다.
- 인간 관절을 그룹화하고 공간적 위치에 따라 상관 관계를 도출한다.
- 모델은 공간적 위치를 사전지식으로 취하여 인간 관절을 그룹화하고 계층적 방식으로 국소 영역의 구별 패턴을 마이닝한다.
- 공간적 관점에서 효율적인 특징 추출을 위해 골격 데이터를 희소 형식으로 변환하고 희소 골격 모델링을 위한 두 가지 유형의 희소 합성곱 네트워크를 제시한다.

# 참고자료 & 논문 등 출처
[인접행렬-나무위키](https://namu.wiki/w/%EC%9D%B8%EC%A0%91%ED%96%89%EB%A0%AC)
[convolutional-networks](https://cs231n.github.io/convolutional-networks/)
[paperswithcode.com](https://paperswithcode.com/)
[Modeling Skeletons from Semantic and Spatial Perspectives for Action Recognition](https://arxiv.org/abs/2004.03259)
[객체 탐지와 행동인식을 이용한 영상내의 비정상적인 상황 탐지 네트워크 논문](https://www.koreascience.or.kr/article/JAKO202106763002085.pdf)
[Spatial Temporal Graph Convolutional Networks for Skeleton-Based Action Recognition 논문](https://arxiv.org/pdf/1801.07455.pdf)
[이상행동 CCTV 영상 AI 데이터 구축 가이드라인](https://aihub.or.kr/sites/default/files/dataGuideline/10.%20%EC%9D%B4%EC%83%81%ED%96%89%EB%8F%99%20CCTV%20%EC%98%81%EC%83%81%20AI%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EA%B5%AC%EC%B6%95%20%EA%B0%80%EC%9D%B4%EB%93%9C%EB%9D%BC%EC%9D%B8.pdf)