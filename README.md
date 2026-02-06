<h1 align="center">ShowUI-π: Flow-based Generative Models as GUI Dexterous Hands</h1>

<p align="center">
  <i align="center">Unified discrete-continuous actions for free-form drag computer use.</i>
</p>

<p align="center">
        &nbsp&nbsp 📑 <a href="https://arxiv.org/abs/2512.24965">Paper</a> &nbsp&nbsp
        | &nbsp&nbsp 🌐 <a href="https://showlab.github.io/showui-pi/">Project Page</a> &nbsp&nbsp
  | &nbsp&nbsp💬 <a href="https://x.com/HuggingPapers/status/2012559851235197024">X (Twitter)</a>&nbsp&nbsp
        | &nbsp&nbsp 📦 <a href="https://huggingface.co/datasets/h-siyuan/ScreenDrag">Dataset</a> &nbsp&nbsp
</p>

> [**ShowUI-π: Flow-based Generative Models as GUI Dexterous Hands**](https://arxiv.org/abs/2512.24965)<br>
> Siyuan Hu†, Kevin Qinghong Lin†, Mike Zheng Shou*<br>
> <br>Show Lab @ National University of Singapore<br>
> † Equal contribution &nbsp; * Corresponding author<br>

## 🔥 Update
- [x] [2026.1.22] We release the [ScreenDrag](https://huggingface.co/datasets/h-siyuan/ScreenDrag) dataset.
- [x] [2026.1.10] Release code and project page.

## Demo
https://github.com/user-attachments/assets/d033cbf3-e577-4f47-9605-9974a7cefcd7

## Overview

ShowUI-π is a 450M flow-based vision-language-action (VLA) model for GUI control. Given a screen observation and a natural language instruction, it generates continuous cursor trajectories — producing smooth clicks and drags directly in pixel space without tokenized coordinates.

The key insight is a unified action representation: both clicks and drags are modeled as cursor waypoint sequences paired with mouse button states (pressed/released). This allows the model to handle discrete click actions and continuous drag operations within a single framework, using flow matching to generate temporally coherent trajectories.

This design enables tasks that require fine-grained spatial control, such as freehand drawing, object rotation, drag-to-sort, slider adjustment, and captcha solving — capabilities that are difficult or impossible for conventional click-only GUI agents.

## Highlights

- **Continuous GUI Control** — Flow matching generates smooth, temporally coherent cursor trajectories in continuous pixel space, going beyond discrete click-only actions.
- **Unified Action Representation** — Clicks and drags are both represented as cursor waypoint sequences with mouse states, eliminating the need for separate action heads.
- **Parameter Efficient** — At 450M parameters, ShowUI-π outperforms 7B+ models on drag-based GUI tasks while remaining lightweight and efficient.
- **ScreenDrag Dataset** — A new benchmark of 505 real-world drag tasks with over 20K trajectories across 5 application domains.

## ScreenDrag Dataset

[ScreenDrag](https://huggingface.co/datasets/h-siyuan/ScreenDrag) is a dataset of real-world screen drag tasks collected to train and evaluate continuous GUI control. It contains 505 tasks with over 20K cursor trajectories, each annotated with full waypoint sequences and mouse button states.

The dataset covers 5 application domains:
- **PowerPoint** — slide editing, object manipulation, shape drawing
- **OS / File Manager** — drag-to-select, file sorting, window resizing
- **Adobe Premiere Pro** — timeline editing, clip rearrangement
- **Captcha** — slider and puzzle-piece drag verification
- **Handwriting** — freehand character drawing and annotation

## Getting Started

```bash
git clone https://github.com/showlab/ShowUI-Pi.git
cd ShowUI-Pi
pip install -e .
```

> Detailed installation, training, and inference instructions are coming soon.

## Acknowledgements

- [LeRobot](https://github.com/huggingface/lerobot) (Hugging Face) — ShowUI-π builds on the LeRobot codebase for flow-based policy learning.
- [ShowUI](https://github.com/showlab/ShowUI) — the predecessor project for vision-language GUI understanding.

## 🎓 BibTeX

If you find our work helpful, please kindly consider citing our paper.

```bibtex
@misc{showuipi,
  title={ShowUI-$\\pi$: Flow-based Generative Models as GUI Dexterous Hands},
  author={Siyuan Hu and Kevin Qinghong Lin and Mike Zheng Shou},
  year={2025},
  eprint={2512.24965},
  archivePrefix={arXiv},
  primaryClass={cs.CV},
  doi={10.48550/arXiv.2512.24965},
  url={https://arxiv.org/abs/2512.24965},
}
```

## License

This project is licensed under the Apache License, Version 2.0.
See `LICENSE` for details.
