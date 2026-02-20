<div align="center">
  <a href="https://video-reason.com/">
    <img src="https://video-reason.com/static/images/VBVR_logo.png" height="100" alt="VBVR Logo"/>
  </a>

  <h1>VBVR-DataFactory</h1>
  <h3>The Scalable Data Engine Behind <a href="https://video-reason.com/">Very Big Video Reasoning</a></h3>

  <p>
    <a href="https://video-reason.com/"><img src="https://img.shields.io/badge/Website-video--reason.com-000000?style=for-the-badge" alt="Website"/></a>
    <a href="https://video-reason.com/"><img src="https://img.shields.io/badge/Paper-VBVR-b31b1b?style=for-the-badge" alt="Paper"/></a>
    <a href="https://huggingface.co/VideoReason"><img src="https://img.shields.io/badge/HuggingFace-VideoReason-FFD21E?style=for-the-badge&logo=huggingface&logoColor=000" alt="HuggingFace"/></a>
    <a href="https://join.slack.com/t/vm-dataset/shared_invite/zt-3mdb2lkye-lm7ZC4OGxxRRMEi1M65hKQ"><img src="https://img.shields.io/badge/Community-Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white" alt="Slack"/></a>
  </p>
</div>

---

## About VBVR

**Very Big Video Reasoning (VBVR)** is a community built on the belief that intelligence is grounded in space and time &mdash; beyond what text can naturally capture. We are building the open infrastructure to study, train, and evaluate reasoning in video generation models.

The VBVR suite consists of three pillars:

| Component | Description | Link |
|:--|:--|:--|
| **VBVR-Dataset** | 2M+ images and 1M+ video clips across 200 curated reasoning tasks &mdash; ~1,000x larger than all prior video reasoning datasets combined | [Data](https://video-reason.com/data/) |
| **VBVR-Bench** | A fully rule-based, deterministic evaluation framework with Spearman &rho; > 0.9 human alignment | [Bench](https://video-reason.com/bench/) |
| **VBVR-Wan2.2** | A strong baseline model achieving 84.6% relative improvement over the base Wan2.2, surpassing all evaluated proprietary models | [Models](https://video-reason.com/models/) |

> This GitHub organization hosts the **DataFactory**: the parameterized task generators and pipeline infrastructure that power VBVR-Dataset at scale.

---

## Scale

<table>
<tr>
<td align="center"><h3>200+</h3>Reasoning Tasks</td>
<td align="center"><h3>2,015,000</h3>Images</td>
<td align="center"><h3>1,007,500</h3>Video Clips</td>
<td align="center"><h3>50+</h3>Contributors Worldwide</td>
</tr>
</table>

---

## Cognitive Architecture

VBVR organizes video reasoning around five foundational cognitive faculties, grounded in established theories from philosophy, cognitive science, and neuroscience:

| Faculty | Definition | Example Tasks |
|:--|:--|:--|
| **Perception** | Extraction of structured representations from sensory input | Edge detection, shape discrimination, color identification |
| **Transformation** | Manipulation and synthesis of mental representations | Mental rotation, object resizing, occlusion simulation |
| **Spatiality** | Representation of places and geometric relationships | Grid navigation, graph traversal, maze solving |
| **Abstraction** | Distillation of generalizable knowledge from particular experiences | Raven's matrices, pattern completion, sequence prediction |
| **Knowledge** | Propositional truths, either learned or innate | Physics simulation, color mixing, chart reading |

---

## How It Works

Every VBVR task is implemented as a **parameterized generator** that deterministically produces four outputs:

```
Generator(seed, params)
    -> first_frame.png     # Initial state (model input)
    -> prompt.txt          # Task instruction (model input)
    -> final_frame.png     # Target state (supervision)
    -> ground_truth.mp4    # Complete solution trajectory (supervision)
```

Generators are executed at scale via distributed cloud workers, writing to centralized storage. The infrastructure supports continuous expansion: new tasks plug into the same pipeline with automated validation and quality control.

```
Cognitive Architecture --> Task Design & Review --> Generator Implementation --> Cloud-Scale Generation
       (5 faculties)        (500+ proposals,           (parameterized,            (distributed Lambda
                             200+ approved)             deterministic)              workers -> S3)
```

---

## Repository Map

### This Organization &mdash; VBVR-DataFactory

| Repository | Description |
|:--|:--|
| [`template-data-generator`](https://github.com/VBVR-DataFactory/template-data-generator) | Starter template for building new task generators. Fork this to contribute a task. |
| [`template-data-pipeline`](https://github.com/VBVR-DataFactory/template-data-pipeline) | Template for preparing external datasets into VBVR-compatible formats. |

### Sister Organization &mdash; [Video-Reason](https://github.com/Video-Reason)

| Repository | Description |
|:--|:--|
| [`VBVR-EvalKit`](https://github.com/Video-Reason/VBVR-EvalKit) | Rule-based evaluation framework for video reasoning models |
| [`VBVR-DataFactory`](https://github.com/Video-Reason/VBVR-DataFactory) | Scalable data generation orchestration |
| [`Awesome-Video-Reasoning`](https://github.com/Video-Reason/Awesome-Video-Reasoning) | Curated collection of papers on reasoning in video generation models |

---

## Getting Started

### Contributing a New Task

1. **Fork** [`template-data-generator`](https://github.com/VBVR-DataFactory/template-data-generator) to get the standardized generator template
2. **Design** your task targeting one of the five cognitive faculties
3. **Implement** a parameterized generator that produces `first_frame.png`, `prompt.txt`, `final_frame.png`, and `ground_truth.mp4`
4. **Submit** your generator for review against our six quality criteria:
   - Information sufficiency
   - Deterministic solvability
   - Video dependency
   - Visual clarity
   - Parametric diversity (10,000+ non-trivial instances)
   - Technical feasibility

### Running Evaluations

See [VBVR-EvalKit](https://github.com/Video-Reason/VBVR-EvalKit) for the full evaluation framework and benchmark results.

### Accessing the Dataset

The dataset is available on [HuggingFace](https://huggingface.co/VideoReason). See our [Data page](https://video-reason.com/data/) for download instructions and dataset statistics.

---

## Benchmark Highlights

Performance of leading models on VBVR-Bench (higher is better):

| Model | Overall | In-Domain | Out-of-Domain |
|:--|:--:|:--:|:--:|
| Human | 0.974 | 0.960 | 0.988 |
| **VBVR-Wan2.2** (ours) | **0.685** | **0.760** | **0.610** |
| Sora 2 | 0.546 | 0.569 | 0.523 |
| Veo 3.1 | 0.480 | 0.531 | 0.429 |
| Runway Gen-4 | 0.403 | 0.392 | 0.414 |
| Wan2.2 (base) | 0.371 | 0.412 | 0.329 |
| Kling 2.6 | 0.369 | 0.408 | 0.330 |

---

## Community

We welcome researchers, engineers, and anyone interested in video reasoning to join our community.

- **Website**: [video-reason.com](https://video-reason.com/)
- **Slack**: [Join our workspace](https://join.slack.com/t/vm-dataset/shared_invite/zt-3mdb2lkye-lm7ZC4OGxxRRMEi1M65hKQ)
- **HuggingFace**: [VideoReason](https://huggingface.co/VideoReason)
- **Contact**: [hokinxqdeng@gmail.com](mailto:hokinxqdeng@gmail.com)

---

## Citation

```bibtex
@article{vbvr2026,
  title={A Very Big Video Reasoning Suite},
  author={Wang, Maijunxian and Wang, Ruisi and Lin, Juyi and Ji, Ran and Wiedemer, Thaddäus and Gao, Qingying and Luo, Dezhi and Qian, Yaoyao and Huang, Lianyu and Hong, Zelong and Ge, Jiahui and Ma, Qianli and He, Hang and Zhou, Yifan and Guo, Lingzi and Mei, Lantao and Li, Jiachen and Xing, Hanwen and Zhao, Tianqi and Yu, Fengyuan and Xiao, Weihang and Jiao, Yizheng and Hou, Jianheng and Zhang, Danyang and Xu, Pengcheng and Zhong, Boyang and Zhao, Zehong and Fang, Gaoyun and Kitaoka, John and Xu, Yile and Xu, Hua and Blacutt, Kenton and Nguyen, Tin and Song, Siyuan and Sun, Haoran and Wen, Shaoyue and He, Linyang and Wang, Runming and Wang, Yanzhi and Yang, Mengyue and Ma, Ziqiao and Millière, Raphaël and Shi, Freda and Vasconcelos, Nuno and Khashabi, Daniel and Yuille, Alan and Du, Yilun and Liu, Ziming and Lin, Dahua and Liu, Ziwei and Kumar, Vikash and Li, Yijiang and Yang, Lei and Cai, Zhongang and Deng, Hokin},
  year={2026}
}
```

---

<div align="center">
  <sub>VBVR is a collaborative effort involving 50+ researchers from 30+ institutions worldwide.</sub>
  <br/>
  <sub>MIT License</sub>
</div>
