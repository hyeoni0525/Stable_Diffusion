# Stable_Diffusion
<h3>Stable Diffusion 기반 이미지 생성에 따른 학습 데이터 효율화 연구</h3>

<p align="center"><img src="https://github.com/user-attachments/assets/61a1d43e-3948-412c-8d08-579a84bb1367"  width="400" height="400"/></p>


# Contents
1. Overview

2. Tech Stack

3. Dataset

4. Experiment

5. Results

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

--------
# Experiment
- 프롬포트 예시:

```
“A photorealistic, highly detailed 8K photograph of a turtle in various settings and poses in the sea, shot with a Nikon Z7 II, 70-200mm lens, natural lighting, sharp focus, ultra-high-definition”
```
- 사전 학습 된 ResNet18을 이용하여 Image Classification을 전이학습 진행

---------
# Results
본 연구에서는 실제 이미지와 Stable Diffusion으로 생성된 인공 이미지의 비율을 조절하여 총 5개의 데이터셋 구성

ResNet18 모델로 학습한 뒤 동일한 테스트셋을 사용하여 성능을 비교 진행

<img src="https://github.com/user-attachments/assets/2c6f26b5-5b0a-49fe-b3c1-68b2b901bb9e"  width="400" height="200"/>
<br>
<img src="https://github.com/user-attachments/assets/18a4f5fa-1dc7-49dc-bd7f-7de566608e47"  width="300" height="300"/>

- 원본 데이터셋에서 가장 높은 정확도를 기록

- 6:4 구성의 데이터셋에서는 실제 데이터에 가까운 성능을 유지하면서도 인공 이미지 데이터를 효과적으로 활용

- 7:3, 8:2 구성의 데이터셋처럼 인공 이미지 데이터의 비율이 높아질수록 정확도 감소
<br>

:white_check_mark: **인공 이미지 비율이 늘어날수록 정확도는 감소했으나, 성능은 일정 수준 유지**

:white_check_mark: **인공 이미지의 비율이 과도해질 경우, 모델의 일반화 성능 저하 가능성 존재**

:white_check_mark: **실제 이미지와 인공 이미지 간의 균형 있는 조합이 중요**

-------
# Conclusion
Stable Diffusion 기반 생성 이미지는 실제 이미지 데이터를 보완할 수 있는 가능성을 확인

추후 생성형 AI가 더 발전하여 이미지 데이터의 특이점을 돌파하게 된다면 원하는 데이터셋을 수집하는데 큰 도움이 될 것으로 기대

