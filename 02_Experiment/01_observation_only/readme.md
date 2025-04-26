# Self-Modifying Quantum Circuit from Observation

## 📘 시스템 개요 | System Overview
- **실험명 (Experiment Title)**: Self-Modifying Quantum Circuit from Observation
- **목적 (Objective)**: 관측 결과 수치에 따라 양자 회로 구조가 스스로 반응하고 수정되는 과정을 검증한다.
- **주요 기능 (Key Functions)**:
  - 회로 실행 중 수집된 결과 데이터(수치/엔트로피)에 기반하여 구조가 자율적으로 변형된다.
  - 구조 반응 유도 메커니즘을 실험적으로 구현한다.

## 🧩 실험 구조 | Experimental Structure
1. RY 게이트 기반 초기 회로 생성
2. 시간 경과에 따른 회로 복잡도 및 구조 변화 관찰
3. 결과가 지정 조건을 충족하지 않을 경우 구조 변경
4. 최대 10회 반복 실행

## 🎯 결정 조건 | Decision Conditions
- **조건 1**: 결과 데이터에서 최대 확률이 60%를 초과하면 구조를 고정한다.
- **조건 2**: 측정된 샤논 엔트로피가 2.2 이하이면 구조를 수정한다.

## 🛠️ 구조 변경 방식 | Structural Modification Rules
- 짝수 반복 회차 (even iterations): Hadamard 게이트 추가
- 홀수 반복 회차 (odd iterations): CNOT 게이트 추가

## 📂 파일 경로 | File Location
```
02.experiments/
└── 02001.self-modifying-observation/
    ├── run_self_modifying.py
    ├── circuit_log.json
    └── README.md
```

## ⚙️ 기본 설정 | Default Settings
- **타겟 환경 (Target Environment)**: Qiskit 1.0.2 + Aer simulator
- **반복 실행 목표 (Iteration Target)**: 최대 10회 반복, 조건 충족 시 조기 종료 가능

## 🕒 흐름 요약 | Process Summary
- 진입: 결과 분기 포인트 관찰 → 구조 변경 여부 판정
- 출력: circuit_log.json 파일에 반복 기록 저장 및 구조 변동 시각화 결과 생성

## ✨ 특징 | Features
- 결과 수치 변화에 따라 구조가 자율적으로 변형되는 '자기 반응적 구조(Self-Responsive Structure)'를 실험한다.
- 엔트로피 변화가 구조 반응 조건으로 작용할 수 있음을 검증한다.

## 🔒 보안 | Safeguards
- 연산자 방식 고정 없이, 엔트로피 및 최대 수치 조건만으로 구조 변경 여부를 결정한다.
- 외부 수치 주입 없이 시스템 내 관측 데이터만으로 반응성을 검증한다.
