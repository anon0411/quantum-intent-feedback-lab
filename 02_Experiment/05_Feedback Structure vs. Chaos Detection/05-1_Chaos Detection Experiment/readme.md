# Chaos Detection Experiment in Rotation-Gate Feedback Quantum Circuits

## 📘 개요 | Overview
본 실험은 양자 회로의 출력 분포에 기반한 회전 게이트 피드백 구조가 반복 수행 중 혼란 상태(chaotic state)로 진입하는지를 확인하기 위한 구조적 실험이다.  
This experiment investigates whether a rotation-gate-based feedback structure in a quantum circuit enters a chaotic state during repeated operations based on output distribution.

각 반복에서 출력 분포를 벡터화하여 이전 분포와의 유사도를 측정하며, 일정 임계치 미만의 유사도가 반복되면 구조가 불안정한 상태에 진입했다고 판단한다.  
In each iteration, the output distribution is vectorized and compared with the previous distribution using cosine similarity. A persistent drop below a threshold indicates a transition into structural instability.

## ⚙️ 실험 설정 | Experimental Setup
- **큐빗 수 (Number of Qubits)**: 3
- **반복 횟수 (Iterations)**: 20
- **측정 샷 수 (Shots per Execution)**: 1024
- **피드백 학습률 (Feedback Learning Rate, η)**: 0.25
- **회전 게이트 (Rotation Gate)**: RY
- **유사도 측정 (Similarity Metric)**: 코사인 유사도 (Cosine Similarity)
- **혼란 기준 (Chaos Criterion)**: 최근 5회 유사도가 모두 0.95 미만일 경우  
If cosine similarity falls below 0.95 for 5 consecutive steps, the system is considered to have entered chaos.

## 🔄 회로 작동 방식 | Circuit Operation
1. 초기 회전값(`theta`)은 무작위로 설정된다.  
   Initial rotation values (`theta`) are randomly initialized.
2. RY 게이트를 적용한 후 측정한다.  
   RY gates are applied based on `theta`, followed by measurement.
3. 측정 결과를 벡터화하여 현재 분포(intent vector)를 생성한다.  
   The output bitstring is transformed into a vector representation.
4. 이전 분포와 코사인 유사도를 계산한다.  
   Cosine similarity is computed with the previous vector.
5. 현재 분포에서 0.5를 뺀 값에 학습률을 곱하여 각 회전값에 피드백을 적용한다.  
   Feedback is applied by nudging rotation angles based on deviation from 0.5.
6. 최근 5회 유사도를 기반으로 혼란 상태 진입 여부를 판단한다.  
   Chaos is detected if the last 5 similarities are all below 0.95.

## 🧪 실험 결과 | Results
### 🔢 최종 회전 각도 (Final Rotation Angles)
```
[-0.5    1.5045  1.495 ]
```

### 📈 출력 상태 벡터 (마지막 5회) | Output Vectors: Last 5 Iterations
```
[0.4883 0.5078 0.5322]
[0.5146 0.5068 0.4863]
[0.5068 0.4902 0.5039]
[0.5146 0.5322 0.5146]
[0.4736 0.5078 0.5098]
```

### 📉 코사인 유사도 흐름 | Cosine Similarity Trend
```
[1.     0.9996 0.9951 0.9982 0.9958 0.9983 0.9914 0.9955 0.9992 0.9996
 0.9982 0.9963 0.9998 0.9986 0.9994 0.9992 0.9983 0.9996 0.9995 0.9996]
```

## 🔍 결과 해석 | Interpretation
- 실험 종료 시점까지 혼란 상태는 감지되지 않았다.  
  No chaotic state was detected throughout the experiment.
- 모든 코사인 유사도가 0.95 이상으로 유지되어 구조가 매우 안정적임을 보여준다.  
  All cosine similarities remained above 0.95, indicating high stability.
- 회전 각도는 일부 큐빗에서 포화 경향을 보였고, 출력 벡터는 0.5 부근에서 진동하며 중심화된 분포를 유지했다.  
  Some rotation angles approached saturation, but the output vector oscillated near 0.5, indicating a centered distribution.
- 피드백 구조는 시스템을 수렴적이고 예측 가능한 동작으로 안정화시켰다.  
  The feedback structure maintained the system in a convergent and predictable regime.

## 📝 결론 | Conclusion
본 실험은 단순한 회전 게이트 기반의 피드백 구조가 반복 실행 후에도 쉽게 혼란 상태로 진입하지 않음을 보여주었다.  
This experiment shows that a simple rotation-gate-based feedback system does not easily transition into chaos over repeated execution.

이는 출력 분포의 중심화를 안정적으로 유도할 수 있는 **자기 유지(self-regulation)** 특성을 가진 회로 설계가 가능함을 시사한다.  
It implies the feasibility of designing self-regulating quantum circuits where internal feedback stabilizes output distributions.

## 🔮 후속 제안 | Further Suggestions
- **혼란 유발 조건 삽입 실험**: 노이즈 주입, 랜덤 게이트 추가  
  Experiments with chaos-inducing conditions (e.g., noise injection, random gates)
- **피드백 구조 변경 실험**: 다양한 게이트 종류, 큐빗 간 상호작용 포함  
  Structural variations: alternative gate types, multi-qubit interaction
- **피드백 중단 또는 역피드백 실험**: 시스템 안정성 한계 분석  
  Feedback suspension or inverse feedback trials
- **출력 분포 시각화 및 동역학 분석**: 진폭 분포의 시각적/수학적 분석  
  Visualization and dynamic analysis of output evolution
