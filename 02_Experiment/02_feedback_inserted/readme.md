# Observation-Driven Quantum Circuit with Embedded Structural Feedback

## 📘 시스템 개요 | System Overview
- **실험명 (Experiment Title)**: Observation-Driven Quantum Circuit with Embedded Structural Feedback

## 🎯 목적 | Objective
- 관측 결과를 단순한 조건 판별이 아닌, 회로 내부에 누적되는 **구조 반응 정보**로 해석한다.
- 반복된 관측을 통해 회로가 스스로 **구조를 변화하거나 유지**하도록 유도한다.
- 대조군 실험과 비교하여 구조 반응 유도 구조의 유효성을 검증한다.

## 🧠 개념 구조 | Conceptual Structure
- **초기 회로**: RY 기반 게이트로 구성된 단순 회로
- **구조 반응 삽입**: 큐빗별 측정 결과를 기반으로 우선도(priority)를 계산
- **회로 반영**: 우선도가 임계치를 초과하면 RY 각도 증폭 또는 CNOT 삽입으로 구조 수정

## 🔄 실험 흐름 | Experimental Flow
1. 초기 회로 생성 (RY 게이트)
2. 측정 결과 수집 (counts)
3. 큐빗별 결과를 기반으로 우선도 갱신 (priority[i][0], priority[i][1])
4. 각 큐빗의 dominant state 비율로 intent[i] 계산
5. intent[i] ≥ 0.7이면 구조 변경, 그렇지 않으면 구조 유지
6. 최대 10회 반복 실행

## 🧪 실험 결과 요약 | Experimental Results Summary
- **Iteration 0**: 세 큐빗 모두 intent > 0.8 → 구조 수정 발생
- **Iteration 1–9**: intent 감소, 기준 미달 → 구조 유지
- **결론**: 회로는 구조 반응 이후 자율 안정화 경향을 보임

## 📈 분포 변화 | Distribution Changes
- **Iteration 0**: `000` 상태로 분포 집중 → 초기 구조 수립
- **Iteration 1 이후**: 전체 상태로 분포 확산 → 집중도 감소
- 구조가 자기 피드백 이후 평형 상태로 이행하는 경향이 시각적으로 확인됨

## 🧠 구조 반응 해석 | Structural Feedback Interpretation
- 구조가 관측 결과를 '구조 변경 조건'으로 해석하고 반응한다.
- 관측 → 피드백 → 구조 결정이라는 순환 구조가 실험적으로 입증되었다.

## 📂 파일 경로 | File Structure
```
02.experiments/
└── 02002.intent-feedback-observation/
    ├── run_intent_feedback.py
    ├── priority_log.json
    └── README.md
```

## ⚙️ 실험 설정 | Experimental Settings
- **큐빗 수 (Number of Qubits)**: 3
- **초기 RY 각도 (Initial RY Angle)**: U[i] = 0.25π
- **우선도 임계값 (Priority Threshold)**: 0.7
- **반복 조건 (Iteration Condition)**: 최대 10회 반복 또는 수렴
- **구조 변화 규칙 (Structural Change Rule)**: RY 각도 +0.25 (최대 1.0)