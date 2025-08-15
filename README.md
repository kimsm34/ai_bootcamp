# 표정 연기 코칭 AI

입력된 문장의 감정과 사용자의 표정을 실시간으로 비교하여 표정 연기를 점수화하는 AI 코칭 프로그램입니다. 이 프로젝트는 2022 OUTTA AI 부트캠프 최종 미션으로 제작되었습니다.

---

## 주요 기능

* 텍스트 감정 분석: 사용자가 입력한 한국어 문장을 KoBERT 모델을 이용해 '공포', '놀람', '분노', '슬픔', '중립', '행복', '혐오'의 7가지 감정으로 분석하고, 가장 확률이 높은 감정을 추출합니다.
* 실시간 표정 분석: 웹캠을 통해 사용자의 얼굴을 탐지하고, CNN 기반의 이미지 분류 모델을 통해 표정을 7가지 감정으로 실시간 분석합니다.
* 코사인 유사도 매칭: 텍스트에서 추출된 7차원 감정 벡터와 표정에서 추출된 7차원 감정 벡터 간의 코사인 유사도를 계산하여 '표정 연기 점수'를 산출합니다.
* 시각적 피드백: OpenCV를 활용하여 웹캠 화면에 사용자의 얼굴, 분석된 표정 감정, 목표 감정, 그리고 실시간 연기 점수를 시각적으로 표시합니다.


---

## 기술 스택

* Natural Language Processing (NLP):
    * `PyTorch`
    * `KoBERT` (from `monologg`)
    * `transformers`, `gluonnlp`, `sentencepiece`
* Computer Vision:
    * `PyTorch`
    * `OpenCV`
    * Custom CNN Model (based on Mini_Xception architecture)
* 개발 환경:
    * Google Colab, Jupyter Notebook
    * Python

---

## 프로젝트 구조

이 프로젝트는 크게 NLP 파트와 Vision 파트로 나뉘며, 각 파트의 기능들이 최종적으로 `main_stream_final.ipynb`에서 통합되어 실행됩니다.

* `nlp_..._final.ipynb`: 텍스트 데이터 전처리, KoBERT 모델 학습 및 감정 예측 기능을 담당합니다.
* `vision_..._final.ipynb`: 이미지 데이터셋(FER2013) 처리, CNN 모델 학습 및 웹캠을 이용한 실시간 표정 예측 기능을 담당합니다.
* `main_stream_final.ipynb`: NLP와 Vision 파트의 기능을 통합하여 전체 애플리케이션을 실행합니다.
