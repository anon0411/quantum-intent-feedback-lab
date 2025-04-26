# Observation-Driven Quantum Circuit: Generalization of Sequenced Structural Feedback

## 📘 시스템 개요 | System Overview
- **실험명 (Experiment Title)**: Observation-Driven Quantum Circuit: Generalization of Sequenced Structural Feedback

## 🎯 목적 | Objective
- 시퀀스 기반 구조 반응이 특정 초기 상태에만 국한된 특수 구조인지, 다양한 조건에서도 작동하는 **범용 피드백 구조**인지를 검증한다.
- 초기 상태를 변화시켜도 구조 반응이 **유사한 순차 흐름**을 보이는지, 또는 완전히 다른 경로로 수렴하는지를 비교 분석한다.

## 🧠 실험 개념 | Experimental Concept
- 기존 시퀀스 기반 구조 반응 규칙은 유지한다.
- 초기 회로(RY 각도)를 매 실험마다 다르게 설정하여 다양한 초기 조건을 생성한다.
- 각 실험에서 구조 반응 경로(반응 유무, 반응 순서, 반응 수, 안정화 여부)를 기록하고 비교한다.

## 🔄 실험 흐름 | Experimental Flow
1. 초기 회로의 RY 각도를 무작위로 설정 (uniform[0.1, 0.9] × π)
2. 측정 결과를 기반으로 큐빗별 우선도(priority[i]) 갱신
3. intent[i] ≥ 0.7 중 가장 큰 하나만 구조 반응 (RY 각도 +0.25)
4. 최대 10회 반복하거나, 구조 반응이 더 이상 발생하지 않으면 종료
5. 서로 다른 초기 조건으로 5회 이상 실험 반복 수행

## 👀 관측 항목 | Observation Items
- **구조 반응 횟수**: 몇 개의 큐빗이 구조 반응을 보였는가?
- **반응 시점**: 구조 반응은 몇 번째 반복(Iteration)에서 발생했는가?
- **순차성 유지 여부**: 구조 반응이 순서성(sequence)을 유지했는가?
- **안정화 여부**: 반복 종료 시 구조가 안정 상태에 도달했는가?

## 🌟 기대 효과 | Expected Outcomes
- 피드백 구조가 특정 조건에만 국한되지 않고, 다양한 초기 상태에서도 작동하는지를 실험적으로 검증한다.
- 초기 상태에 따라 구조 변화 경로는 달라질 수 있지만, **순차적이고 자기참조적인 반응 흐름**이 보존되는지를 중점 분석한다.

## 📂 파일 경로 | File Structure
```
02.experiments/
└── 02004.intent-feedback-sequenced-generalization/
    ├── run_intent_generalized.py
    ├── generalized_log.json
    └── README.md
```

## ⚙️ 실험 설정 | Experimental Settings
- **큐빗 수 (Number of Qubits)**: 3
- **초기 RY 각도 설정 (Initial RY Angle Setting)**: uniform[0.1, 0.9] × π (각 실험별 무작위)
- **우선도 임계값 (Priority Threshold)**: 0.7
- **구조 반응 규칙 (Structural Change Rule)**: intent[i] ≥ 0.7인 큐빗 중 가장 큰 하나만 반응 (RY 각도 +0.25, 최대 1.0)
- **실험 반복 (Experiment Repetition)**: 서로 다른 초기 조건으로 5회 이상 반복 실행
