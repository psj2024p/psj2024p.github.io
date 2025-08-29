---
title: "AI Model Performance"
date: 2025-08-29 14:33:33 +0900
categories: [기술]
tags: [RAG]
toc: true
comments: false
mermaid: true
math: true
---

# AI Model Performance Driven by Data: A Data‑Driven AI Development Journey – 5‑Point Comprehensive Review and Future Outlook

> **\"데이터가 없으면 AI는 부정확해집니다.\"**
> \- 데이터와 연구자, 훈련비용

---

## 1️⃣ 부가적 – 시각 데이터 시작이 AI 성과의 핵심이냐?

AI 모델은 **데이터**를 바탕으로 학습하지만, 그 데이터가 모델 성과를 좌우합니다. 

> **핵심 질문**
> *데이터 시작과 적용에서 얼마나 중요한가?*

이 부분에서 **데이터 시작 적용**을 중심으로 설명하고, 5가지 전반적인 관점을 제시합니다. PDF에 추가된 핵심 문헌을 살펴보면, 데이터 수집이 핵심이라는 점을 확인할 수 있습니다.

---

## 2️⃣ 부가적 1 – 데이터 수집: 목록화 단계

| 항목 | 부가적 | 전반적 |
|------|-----------|--------|
| **1. 목록 정리** | *데이터가 충분히 있을 때 주제 설정* | **핵심**: \"이 데이터는 모든 비밀을 가지고 있나요?\" |
| **2. 데이터 수집** | *실제 데이터 + 웹 스크래핑 + 생성 데이터* | **코드**: `requests + BeautifulSoup` |
| **3. 수집 설정** | *수집 설정* | **예시**: \"정확성, 신뢰성, 재현성\" |

> **부가적 인사이트**
> - **목록 정리**는 데이터 수집을 가이드합니다.
> - **실제 데이터**와 **생성 데이터**를 결합하면 신뢰성을 높일 수 있습니다.
> - **수집 설정**은 데이터 품질을 보장합니다.

---

## 3️⃣ 부가적 2 – 데이터 활용: 수집, 학습, 평가, 생성, 배포

### 3.1 수집

- **CV**: 객체 탐지 (Object Detection)
- **NLP**: 명명된 개체 인식 (Named Entity Recognition)

> **실행 예시**
> ```python
> # CV 수집 예시 (YOLOv5)
> !pip install ultralytics
> from ultralytics import YOLO
> model = YOLO('yolov5s.pt')
> model.train(data='dataset.yaml', epochs=10)
> ```

### 3.2 학습

- **오류 수집**: 부정확한 데이터, 누락 데이터
- **정확도 평가**:
> 1. **정밀도** (IoU 기준)
> 2. **재현율** (정확도)

### 3.3 생성

- **Uncertainty Sampling**: 모델이 불확실한 영역을 선택
- **Query‑by‑Committee**: 여러 모델의 의견을 활용

> **코드 예시**
> ```python
> from modAL.models import ActiveLearner
> from sklearn.ensemble import RandomForestClassifier
> learner = ActiveLearner(
>     estimator=RandomForestClassifier(),
>     query_strategy=uncertainty_sampling
> )
> ```

> **부가적 인사이트**
> - **생성**은 30% 이하의 비용으로 활용됩니다.
> - **배포**는 5% 정도의 성능 향상을 기대합니다.

---

## 4️⃣ 부가적 3 – 생성 모델과 활용: 데이터 생성과 활용

| 항목 | 부가적 | 전반적 |
|------|-----------|--------|
| **1. 데이터 생성** | JSON, CSV, TFRecord | **예시**: `dataset.yaml` |
| **2. 메타데이터** | *배포, 문서화* | **예시**: README, LICENSE |
| **3. 배포** | GitHub, Kaggle, Hugging Face | **관리**: `git-lfs` |

> **부가적 인사이트**
> - **데이터 배포**는 사용자와 협업을 촉진합니다.
> - **메타데이터**를 잘 관리하면 사용자 만족도를 높일 수 있습니다.

---

## 5️⃣ 부가적 3 – 실제 사용과 비용

| 항목 | 부가적 | 전반적 |
|------|-----------|--------|
| **1. 데이터 수집** | JSON, CSV, TFRecord | **예시**: `dataset.yaml` |
| **2. 메타데이터** | *배포, 문서화* | **예시**: README, LICENSE |
| **3. 배포** | GitHub, Kaggle, Hugging Face | **관리**: `git-lfs` |

> **부가적 인사이트**
> - **데이터 배포**는 사용자와 협업을 촉진합니다.
> - **메타데이터**를 잘 관리하면 사용자 만족도를 높일 수 있습니다.

---

## 6️⃣ 실제 사용과 비용

| 시나리오 | 적용 | 예시 |
|------|-----------|--------|
| **데이터 활용** | **생성 데이터 + 평가** | **비용**: 3개월
| **수집** | **오류 + 정확도** | **비용**: 5% |
| **배포** | **정확도** | **비용**: 20% |

> **사용자 질문**
> - \"이 데이터가 충분히 있나요?\"
> - \"생성 데이터는 실제로 사용 가능한가요?\"

---

## 7️⃣ 부가적 4 – 미래 전망과 질문

> **\"데이터가 없으면 AI는 부정확해집니다.\"**
> 데이터 시작 → 목록 정리 → 수집 → 학습 → 평가 → 생성 → 배포

| 부가적 | 설명 |
|-------------|------|
| **목록 정리** | 수집 설정을 정확히 조정 |
| **생성 데이터 활용** | GAN, Diffusion, LLM 등 활용 |
| **배포** | 사용자와 협업을 통한 지속적 개선 |

> **미래 전망**
> - 데이터 시작이 AI의 핵심입니다.
> - 데이터 수집과 활용을 체계적으로 관리하면 비용을 최소화하면서 성능을 극대화할 수 있습니다.

---

## Samsung Stock Price

- **Ticker:** 005930 (KOSPI)
- **Price:** **70,150 KRW** per share
- **Source:** Investing.com (KOSPI listing)
