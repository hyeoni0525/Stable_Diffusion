# Stable_Diffusion
<h3>Stable Diffusion 기반 이미지 생성에 따른 학습 데이터 효율화 연구</h3>

생성형 AI인 Stable Diffusion을 활용해 인공 데이터를 생성하고, 이를 실제 데이터와 조합하여 학습 성능을 실험

# Contents
1. Overview

2. Tech Stack

3. Dataset

4. Experiment

5. Result

6. Conclusion

7. Reference
-----
# Overview
<img src="https://github.com/user-attachments/assets/76d52e9f-b6cb-4a77-8d12-b472d9343ec7"  width="300" height="300"/>
<img src="https://github.com/user-attachments/assets/b7c57730-f58a-400a-a3dc-248f7af8535e"  width="300" height="300"/>


- 실제 이미지 데이터셋 수집의 한계를 보완하기 위해, Stable Diffusion으로 생성한 인공 이미지를 학습 데이터에 적용
- 인공 이미지의 비율을 조정하며 ResNet18 기반 모델 성능 비교

-----
# Tech Stack
**Requirements**
| Package       | Version  | 설명 (Description)     |
| ------------- | -------- | -------------------- |
| Python        | ≥ 3.8    | 인터프리터 (Interpreter)  |
| torch         | ≥ 1.12.0 | PyTorch 딥러닝 프레임워크    |
| torchvision   | ≥ 0.13.0 | PyTorch 비전 모델 및 유틸리티 |
| opencv-python | ≥ 4.5    | 이미지/비디오 처리 (cv2)     |
| numpy         | ≥ 1.20   | 수치 연산 라이브러리          |
| Pillow        | ≥ 9.0    | 이미지 입출력 및 전처리        |
| scikit-learn  | ≥ 1.0    | ML 평가 지표 및 데이터 분할    |
| matplotlib    | ≥ 3.4    | 시각화 (혼동 행렬 등)        |
| tqdm          | ≥ 4.60   | 진행률 표시바              |

-------
# Dataset
총 클래스: 6개 (곰, 개, 고양이, 거북이, 사슴, 독수리)

데이터 구성:
학습: 1348장
검증: 162장
테스트: 162장

데이터 비율 구성:
실제 100%
인공:실제 = 5:5, 6:4, 7:3, 8:2
