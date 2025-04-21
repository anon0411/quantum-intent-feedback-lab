# 시험: 피드백 구조와 고정 구조 비교 실험  
## Experiment: Comparison Between Feedback-Based and Fixed Quantum Circuits

---

## 시험 목적 (Purpose)

피드백 구조를 가진 양자 회로가 구조적 진화를 하거나 출력 패턴을 안정화할 수 있는지를 검증하고, 구조 없이 반복만 수행하는 고정 회로와 비교하여 구조의 역할과 효과를 평가합니다.

To examine whether feedback in a quantum circuit enables structural evolution or stabilization of output patterns, we compare a feedback-updating circuit with a fixed-parameter circuit under identical conditions.

---

## 시험 구성 (Setup)

- 샷 수 (shots): 1024
- 동일한 초기 상태를 가진 두 개 회로:
  - **회로 A**: 출력 결과에 따라 회전값을 조정하는 피드백 구조
  - **회로 B**: 회전값을 고정한 구조 (피드백 없음)
- 초기 RY 회전각은 [0, 1) 범위에서 무작위로 선택됨
- 피드백 업데이트 수식: `theta += η (output_vector - 0.5)`
- 출력의 변화는 코사인 유사도 (cosine similarity)로 측정

---

## 결과 (Results)

### 회로 A: 피드백 구조 (Circuit A: Feedback-Based)
- **최종 회전값**: `[1.5042, -0.5067, 1.503]`
- **최근 5회 출력 벡터**:
  - [0.5, 0.5137, 0.5078]
  - [0.4961, 0.5029, 0.4971]
  - [0.5049, 0.5, 0.5195]
  - [0.4658, 0.5117, 0.5127]
  - [0.5586, 0.4795, 0.4863]
- **코사인 유사도 흐름**:
  - [1.0, 0.9968, 0.9939, 0.9951, 0.9939, 0.996, 0.9947, 0.9945, 0.9917, 0.9959, 0.995, 0.9998, 0.9996, 0.9998, 0.9994, 0.9995, 1.0, 0.9998, 0.9991, 0.9935]

#### 분석 (Interpretation)
- 출력 결과가 0.5를 중심으로 유지되며 구조가 미세하게 조정되고 있음
- 유사도 흐름은 절대적이지 않지만 구조 반응성과 조정 가능성을 보여줌

> Feedback-induced updates led to dynamic adjustments around the center (0.5), demonstrating structural sensitivity and non-static behavior. The system resists collapse into extremes.

---

### 회로 B: 고정 구조 (Circuit B: Fixed)
- **최종 회전값**: `[0.6245, 0.3288, 0.9093]`
- **최근 5회 출력 벡터**:
  - [0.6758, 0.2773, 0.9883]
  - [0.6953, 0.2598, 0.9863]
  - [0.7021, 0.2441, 0.9746]
  - [0.7256, 0.2451, 0.9785]
  - [0.6934, 0.249, 0.9727]
- **코사인 유사도 흐름**:
  - [1.0, 0.9998, 0.9995, 0.9996, 0.9999, 1.0, 1.0, 1.0, 0.9999, 0.9998, 0.9997, 0.9993, 0.9993, 0.9997, 0.9999, 0.9995, 0.9998, 0.9999, 0.9999, 0.9998]

#### 분석 (Interpretation)
- 회전값이 고정되어 있는 동안 출력은 특정 방향으로 점차 편향되며, 구조적 수렴 경향을 보임
- 피드백 부재로 인해 구조적 다양성이나 자기 조정 능력은 나타나지 않음

> In the absence of feedback, the fixed structure leads to increasing deviation and polarization in output vectors, showing structural rigidity and biased convergence.

---

## 결론 (Conclusion)

- 피드백 구조를 가진 회로는 입력에 따라 구조를 스스로 조정하며 안정된 출력을 유지함
- 고정 구조는 피드백이 없으므로 출력이 편향되고 구조적 왜곡이 누적됨
- 코사인 유사도를 통한 비교에서, 피드백 회로가 더 풍부한 구조 반응성과 조정성을 가지며, 고정 회로는 단순 반복과 수렴만을 보임

Feedback-enabled circuits show adaptive behavior and internal change, while fixed circuits remain static. This highlights the potential for structural plasticity in quantum circuits when feedback mechanisms are included.

---

