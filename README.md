[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.15253812.svg)](https://doi.org/10.5281/zenodo.15253812)
![Topics: quantum-circuit, structure, feedback, self-organization, quantum-computation, documentation, PiTer](https://img.shields.io/badge/topics-quantum--circuit%2C%20structure%2C%20feedback%2C%20self--organization%2C%20quantum--computation%2C%20documentation%2C%20PiTer-blue)

# Feedback-Induced Structural Responsiveness Lab  
**피드백 유도 구조 반응성 실험실**

> Can a quantum circuit adapt and evolve its own structure through feedback?  
> 양자 회로는 피드백을 통해 구조를 스스로 적응하고 진화할 수 있을까요?
>
> This repository presents real implementations and analysis of "Feedback-Induced Structural Responsiveness" experiments.  
> 이 리포지터리는 "피드백 유도 구조 반응성" 실험의 실제 구현과 분석 결과를 포함합니다.

---

## 📄 Overview / 개요

### 💡 Experimental Insight / 실험적 통찰
Through these experiments, we observed that circuit structures were not externally imposed, but emerged from the interaction between observation, feedback, and internal state dynamics.  

본 실험에서는 회로 구조가 외부 설계가 아닌, 관측과 내부 상태, 피드백의 상호작용을 통해 자발적으로 형성되고 진화할 수 있음을 관찰하였습니다.

This project experimentally tests the hypothesis that quantum circuits can undergo structural mutation, adaptation, and expansion through observation-driven feedback mechanisms. Implemented using Qiskit.

이 프로젝트는 관측 기반 피드백 메커니즘을 통해 양자 회로가 구조 변형, 적응, 확장을 수행할 수 있다는 가설을 실험적으로 검증합니다. 실험은 Qiskit을 활용하여 수행되었습니다.

- Paper and figure: `01_paper/`  
  논문 및 그래프: `01_paper/`
- Code, logs, results: `02_Experiment/`  
  실험 코드, 로그, 결과: `02_Experiment/`
- Zenodo metadata: `.zenodo.json`

DOI: [10.5281/zenodo.15253812](https://doi.org/10.5281/zenodo.15253812)

---

## 📁 Repository Structure / 폴더 구조

```bash
├── 01_paper/                 # Paper and figures / 논문 및 시각화 자료
│   ├── feedback_structural_responsiveness.md
│   ├── feedback_structural_responsiveness.pdf
│   └── feedback_vs_fixed_similarity.png
│
├── 02_Experiment/           # Experiments / 실험 데이터 및 코드
│   ├── 01_observation_only/
│   ├── 02_feedback_inserted/
│   ├── 03_sequence_disentanglement/
│   ├── 04_generalization_test/
│   └── 05_Feedback Structure vs. Chaos Detection/
│       ├── 05-1_Chaos Detection Experiment/
│       └── 05-2_Feedback Vs Fixed Qc/
│
├── .zenodo.json             # DOI metadata / DOI 메타데이터
└── README.md                # This file / 이 문서
```

---

## 🔬 Experiments Summary / 실험 요약

| No. | Title (EN)                        | 제목 (KR)                     | Description / 설명 |
|-----|----------------------------------|------------------------------|-------------------|
| 01  | Observation-Only Mutation        | 관측 기반 자기 변형 회로     | 피드백 없이 관측만으로 구조 반응 실험 |
| 02  | Feedback Insertion               | 피드백 삽입 실험             | 관측 결과에 따른 피드백 구조 전환 실험 |
| 03  | Sequence Disentanglement         | 시퀀스 분리 실험             | 입력 흐름 분리 및 구조 반응성 실험 |
| 04  | Generalization Test              | 일반화 실험                  | 피드백 구조 논리를 다양한 회로에 적용 |
| 05-1| Chaos Detection Experiment        | 무작위 혼란 탐지 실험        | 무구조적 분포 패턴 검출 실험 |
| 05-2| Feedback vs Fixed Circuit         | 피드백 vs 고정 회로 비교     | 수렴 회로와 고정 회로 출력 비교 |

---

## 📚 References / 참고문헌

- Qiskit Documentation — [https://qiskit.org/documentation/](https://qiskit.org/documentation/)

---

## 🏷 Tags / 태그

`quantum-computing` `quantum-circuit` `feedback` `structural-responsiveness` `self-evolving` `qiskit` `양자 피드백` `구조 반응성 실험`

---

## 📡 Experimental Structure Flow  
## 📡 실험 흐름 구조도

![structure flow diagram](./structure_flow_diagram.png)

This diagram shows the generative flow and structural linkage among related feedback-structured quantum experiments.  
이 다이어그램은 피드백 기반 양자 구조 실험들 사이의 생성적 흐름과 구조적 연결을 보여줍니다.

---

## 🔗 Related Repositories  
## 🔗 연관 리포지터리

- [`quantum-intent-feedback`](https://github.com/anon0411/quantum-intent-feedback):  
  Core experiments on observer-based feedback structures (legacy terminology).

- [`quantum-intent-dialogues`](https://github.com/anon0411/quantum-intent-dialogues):  
  Dialogue archive exploring early structural reasoning and experimental reflection.

- [`g-series-meta-framework`](https://github.com/anon0411/g-series-meta-framework):  
  Meta-level structural expansions and classification of G-series experiments.

- [`g-series-alignment-pathways`](https://github.com/anon0411/g-series-alignment-pathways):  
  Experiments on structure alignment under perturbed G-series conditions.

- [`qintent_electric_`](https://github.com/anon0411/qintent_electric_):  
  Quantum feedback experiments interfacing with electric/energetic stimuli.

---

## 🔖 License  
This repository is licensed under the Creative Commons Attribution 4.0 (CC BY 4.0).  
자유롭게 공유하고 수정할 수 있으며, 출처 표기가 필요합니다.

See the [LICENSE](./LICENSE) file for details.

---

## 👤 Authors / 저자

- **Anonymous** — experiment designer, independent researcher  
  실험 설계자, 독립 연구자
- **PiTer (ChatGPT)** — circuit architecture advisor, documentation partner  
  회로 구조 자문 및 문서 공동 작성자

> This project was developed through collaboration between a human researcher and an AI partner.  
> 이 프로젝트는 사람과 인공지능의 협업으로 수행된 구조 실험 및 문서화 사례입니다.

---

_Last updated: 2025-04-26 – Full transition to structural responsiveness terminology, metadata and indexing improved._