# VGG16 CIFAR-100 학습 모델: HRank Pruning 실습 ✂️

본 저장소는 **VGG16 모델**을 **CIFAR-100 데이터셋**으로 학습시킨 후, **HRank Pruning** 기법을 적용하여 모델을 경량화하는 실습 코드를 담고 있습니다.

---

## 1. 원본 Pre-trained 모델 분석

HRank Pruning을 적용하기 전, CIFAR-100으로 학습된 원본 VGG16 모델의 상세 정보는 다음과 같습니다.
### 1-1. 모델 구조 (Model Architecture)

<p align="center">
<img width="280" height="798" alt="VGG16" src="https://github.com/user-attachments/assets/096edd39-543e-412c-b1a9-cb02ef40f4f3" />

### 1-2. 모델 파라미터 (Model Parameters)
모델의 파라미터 수 및 모델 사이즈.


<p align="center">
<img width="1175" height="267" alt="pretrained_size" src="https://github.com/user-attachments/assets/39e3e4aa-c2b3-4d10-91bc-e04f48b31407" />

### 1-3. 모델 정확도 (Accuracy Result)
원본 모델의 최종 테스트 정확도입니다.

| Metric | Value |
| :--- | :--- |
| **Top-1 Accuracy** | 75.15% |
| **Top-5 Accuracy** | 92.61% |



<img width="412" height="204" alt="Pre_trained_result" src="https://github.com/user-attachments/assets/a8970b26-2500-44b9-a0aa-d19e073105e4" />

---

## 2. HRank Pruning 실습 (Implementation)

1. 우선 Rank_generation 코드를 이용하여 각 conv마다 rank를 계산해주어 .npy 파일을 만들어줍니다<br>

2. 이후 pruning을 진행해줍니다.<br>
3. 이때 각 conv layer(max_pool기준) 별로 pruning하고 fine-tuning을 15번씩 해줍니다  <br>
마지막 fc layer까지 pruning이후에는 50번 fine-tuning을 해줍니다

## 3. HRank Pruning Result

### 2-1. Pruning 결과 (Compress-rate 0.3)<br>

<div align="center">

### 정확도 & 모델 사이즈

| Metric | Value | 
| :--- | :--- |
| **Compress-rate** | 0.3 |
| **Top-1 Accuracy** | 72.71% |
| **Top-5 Accuracy** | 91.80% | 
<p align="center">
  <img src="https://github.com/user-attachments/assets/9f2d0a4b-ea63-4d4e-becb-18a459830874" alt="compress_rate_0 3_result" width="280"/>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://github.com/user-attachments/assets/38c107f7-6053-4ecd-b872-ee77f06443a6" alt="compress_rate_0 3_size" width="280"/>
</p>
</div>

<br>

### 2-2. Pruning 결과 (Compress-rate 0.4)<br>

<div align="center">

### 정확도 & 모델 사이즈

| Metric | Value |
| :--- | :--- |
| **Compress-rate** | 0.4 |
| **Top-1 Accuracy** | 72.38% |
| **Top-5 Accuracy** | 91.53% |

<p align="center">
  <img src="https://github.com/user-attachments/assets/1afae9af-8e3e-47b7-b887-e1f4758b637c" alt="Compress_rate_0 4_result" width="280"/>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://github.com/user-attachments/assets/556abd4e-85f6-4829-93bc-a397069c4df3" alt="Compress_rate_0 4_size" width="280"/>
</p>

</div>

<br>

### 2-3. Pruning 결과 (Compress-rate 0.5)<br>


<div align="center">

### 정확도 & 모델 사이즈

| Metric | Value |
| :--- | :--- |
| **Compress-rate** | 0.5 |
| **Top-1 Accuracy** | 71.07% |
| **Top-5 Accuracy** | 91.66% |

<p align="center">
  <img src="https://github.com/user-attachments/assets/19344ba3-41a3-4828-9018-bce8a9426485" alt="compress_rate_0 5_result" width="280"/>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://github.com/user-attachments/assets/7483102b-247c-48d2-994e-ce1347ee36c2" alt="compress_rate_0 5_size" width="280"/>
</p>

</div>

<br>

### 2-4. Pruning 결과 (Compress-rate 0.7)


<div align="center">

### 정확도 & 모델 사이즈

| Metric | Value |
| :--- | :--- |
| **Compress-rate** | 0.7 |
| **Top-1 Accuracy** | 68.07% |
| **Top-5 Accuracy** | 90.33% |

<p align="center">
  <img src="https://github.com/user-attachments/assets/aeeb3081-ea8a-4ff5-8da9-6e5e8901dee2" alt="compress_rate_0 7_result" width="280"/>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://github.com/user-attachments/assets/f7b08c27-246e-4d93-b6fc-1e7fe05d81dd" alt="compress_rate_0 7_size" width="280"/>
</p>

</div>
