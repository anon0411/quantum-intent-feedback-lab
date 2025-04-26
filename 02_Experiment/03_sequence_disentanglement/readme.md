# Observation-Driven Quantum Circuit with Sequenced Structural Feedback

## 📘 시스템 개요 | System Overview
- **실험명 (Experiment Title)**: Observation-Driven Quantum Circuit with Sequenced Structural Feedback

## 🎯 목적 | Objective
- 회로가 모든 큐빗에 대해 동시에 반응하는 것이 아니라, **반응 우선도가 높은 큐빗부터 순차적으로 구조 반응**하도록 유도한다.
- 피드백에 의한 구조 반응이 **누적되고 구분 가능한 시퀀스(sequence)**로 나타나는지 확인한다.
- 피드백 구조가 단발성 변화로 끝나지 않고, **지속적이고 계단식 반응 구조**로 발전할 수 있는지 검증한다.

## 🧠 개념 구조 | Conceptual Structure
- **초기 회로**: RY 기반 게이트로 구성된 단순 회로
- **우선도 계산**: 측정 결과에 따라 큐빗별 우선도(priority[i]) 계산
- **구조 반영 규칙**:
  - intent[i] ≥ 임계값(0.7)인 큐빗 중 **가장 높은 하나**만 구조 반응
  - 선택된 큐빗만 다음 반복에서 RY 각도 증폭
  - 다른 큐빗은 구조 유지

## 🔄 실험 흐름 | Experimental Flow
1. 초기 회로 생성 (RY 게이트)
2. 측정 결과 수집 (counts)
3. 큐빗별 우선도 갱신 (priority[i][0], priority[i][1])
4. intent[i] 계산 후, 가장 높은 큐빗 선정
5. 선정된 큐빗만 구조 반응 (RY 각도 +0.25)
6. 최대 10회 반복 실행 또는 수렴 시 종료

## 🌟 기대 효과 | Expected Outcomes
- 각 큐빗의 구조 반응이 시간에 따라 **구분 가능하게 누적**된다.
- 회로 전체가 동시에 변형되지 않고, **선별적, 누적적, 시퀀스 기반 구조 반응**을 보인다.
- 자기 피드백이 단발성 반응이 아니라, **의도적 순차적 반응 메커니즘**으로 발전 가능함을 실험적으로 검증한다.

## 📂 파일 경로 | File Structure
```
02.experiments/
└── 02003.intent-feedback-sequenced/
    ├── run_intent_sequence.py
    ├── sequence_log.json
    └── README.md
```

## ⚙️ 실험 설정 | Experimental Settings
- **큐빗 수 (Number of Qubits)**: 3
- **초기 RY 각도 (Initial RY Angle)**: U[i] = 0.25π
- **우선도 임계값 (Priority Threshold)**: 0.7
- **반복 조건 (Iteration Condition)**: 최대 10회 반복 또는 수렴
- **구조 반응 규칙 (Structural Change Rule)**: intent[i] ≥ 0.7인 큐빗 중 가장 높은 하나만 RY 각도 +0.25 (최대 1.0)