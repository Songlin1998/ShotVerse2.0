# Making MLLM Latents Matter: Factor-Aware Predictive Learning for Cinematic Video Generation


<p align="center">
  <a href="https://arxiv.org/abs/2610.30926"><img src="https://img.shields.io/badge/arXiv-2610.30926-b31b1b.svg" alt="arXiv"></a>
  <a href="https://arxiv.org/html/2610.30926"><img src="https://img.shields.io/badge/Paper-HTML-00a2ff.svg" alt="Paper"></a>
  <!-- TODO: 替换为真实的项目主页与代码仓库地址 -->
  <a href="https://github.com/<org>/FAPL"><img src="https://img.shields.io/badge/Project-Page-green.svg" alt="Project Page"></a>
  <a href="https://github.com/<org>/FAPL"><img src="https://img.shields.io/badge/Code-Coming%20Soon-orange.svg" alt="Code"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="License"></a>
</p>

<p align="center">
  <strong>Songlin Yang<sup>1,*</sup> &nbsp; Zhe Wang<sup>1,*</sup> &nbsp; Xiaotong Zhao<sup>2</sup> &nbsp; Xi Wang<sup>3</sup> &nbsp; Ran Zhang<sup>2</sup> &nbsp; Shuai Li<sup>2</sup><br>
  Taiyi Wu<sup>2</sup> &nbsp; Songlian Li<sup>2</sup> &nbsp; Eric Liu<sup>2</sup> &nbsp; Alan Zhao<sup>2</sup> &nbsp; Anyi Rao<sup>1,†</sup></strong>
</p>

<p align="center">
  <sup>1</sup>MMLab@HKUST, The Hong Kong University of Science and Technology &nbsp;·&nbsp;
  <sup>2</sup>Tencent Video &nbsp;·&nbsp;
  <sup>3</sup>LIX, École Polytechnique
</p>

<p align="center"><sup>*</sup>Equal contribution &nbsp;·&nbsp; <sup>†</sup>Project lead</p>

---

## TL;DR

**FAPL** (Factor-Aware Predictive Learning) makes MLLM representations *actually usable* by a Video DiT for cinematic video generation. It targets two capabilities — **temporal inference from limited inputs** and **factor-aware control** of character / scene / action / camera — with three training stages and **no architectural changes**:

1. **Stage I — MLLM-Only Generator Grounding**: freeze MLLM + connector, train the DiT with MLLM latents as the *sole* content condition.
2. **Stage II — Factor-Aware Control Improvement**: factor-span replacement between paired edits supervises *what should change* and *what should be preserved*.
3. **Stage III — Prediction From Limited Inputs**: freeze the trained DiT, optimize MLLM + connector through it, with text-only and text-plus-complete-video observations sharing one video target.

Built on **UniVideo (13B DiT)**, FAPL improves Motion Order from 48% → **61%**, ∩-Acc from 42% → **58%**, and FaceSim-Arc from 0.451 → **0.523**.

---

## News

- **2026-10-22**: arXiv preprint released. [[arXiv](https://arxiv.org/abs/2610.30926)] [[HTML](https://arxiv.org/html/2610.30926)]
- **TODO**: code, checkpoints, and `CineFactor-10K` evaluation prompts release.

---

## TODO

- [ ] Release training and inference code
- [ ] Release `CineFactor-10K` evaluation prompts
- [ ] Release Stage I–III checkpoints
- [ ] Release project page with video demos

## Citation

```bibtex
@misc{yang2026makingmllmlatentsmatter,
      title={Making MLLM Latents Matter: Factor-Aware Predictive Learning for Cinematic Video Generation}, 
      author={Songlin Yang and Zhe Wang and Xiaotong Zhao and Xi Wang and Ran Zhang and Shuai Li and Taiyi Wu and Songlian Li and Eric Liu and Alan Zhao and Anyi Rao},
      year={2026},
      eprint={2610.30926},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2610.30926},}
```

## Acknowledgements

We build upon [UniVideo](https://github.com/) and compare with [Omni-Video 2](https://arxiv.org/abs/2602.08820). Our training and evaluation data draw on [CoinVE-200K](https://arxiv.org/abs/2608.17566) and [OmniVBench](https://arxiv.org/abs/2609.22069); multi-shot evaluation uses [ShotVerse-Bench](https://arxiv.org/abs/2603.11421). Metrics follow [VBench-2.0](https://arxiv.org/abs/2503.21755), [FiVE](https://arxiv.org/abs/2503.13684), and [π³](https://arxiv.org/abs/2507.13347).

## License

This project is released under the [MIT License](LICENSE). Model checkpoints and dataset usage may be subject to the licenses of the underlying backbones and data sources.
