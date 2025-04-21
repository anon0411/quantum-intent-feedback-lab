# Observation-Driven Quantum Circuit with Embedded Intent Feedback

## 실험 명
- Observation-Driven Quantum Circuit with Embedded Intent Feedback

## 목적
- 관측 결과를 단순한 조건 판별이 아닌, **회로 내부에서 누적되는 '의도' 정보**로 해석
- 반복된 관측을 통해 회로가 스스로 구조를 **변화 또는 유지**하도록 유도
- 대조군 실험과 비교하여 의도 피드백 구조의 유효성을 검증

## 개념 구조
- 초기 회로: RY 기반 게이트로 구성된 단순 회로
- 의도 피드백 구조 삽입: 큐빗별 측정 결과를 기반으로 우선도(priority)를 계산
- 회로 반영: 우선도가 임계치를 넘으면 RY 각도 증폭 또는 CNOT 삽입으로 구조 수정

## 실험 흐름
1. 초기 회로 생성 (RY 게이트)
2. 측정 결과 수집 (counts)
3. 큐빗별 우선도 갱신 (priority[i][0], priority[i][1])
4. 각 큐빗의 dominant state 비율 → intent[i] 계산
5. intent[i] ≥ 0.7이면 구조 변경, 그렇지 않으면 구조 유지
6. 반복 (최대 10회)

## 실험 결과 요약
- **Iteration 0**: 세 큐빗 모두 intent > 0.8 → 구조 조정 발생
- **Iteration 1–9**: intent 감소, 모두 기준 미달 → 구조 유지
- **의미**: 회로는 의도적 구조 반응 이후 자기 안정화됨

## 분포 변화 (시각적 경향)
- Iteration 0: `000` 상태로 분포 집중 → 초기 의도 생성
- Iteration 1 이후: 전체 상태로 균일 분포 확산 → 집중도 감소
- 구조가 자기 피드백 후 평형 상태로 이행한 흐름이 시각적으로 확인됨

## 의도 피드백 구조 해석
- 구조가 관측을 '반응 조건'이 아닌 '자기 상태 인식'으로 전환함
- 관측 = 피드백 = 구조 결정 → 회로의 자기참조성이 작동함을 실험적으로 입증

## 파일 구조
```
02.experiments/
└── 02002.intent-feedback-observation/
    ├── run_intent_feedback.py
    ├── priority_log.json
    └── README.md
```

## 실험 설정
- 큐빗 수: 3
- 초기 각도: U[i] = 0.25π
- 우선도 임계값: 0.7
- 반복 조건: 최대 10회 또는 수렴
- 변화 조건 시: RY 각도 +0.25 (최대 1.0)

