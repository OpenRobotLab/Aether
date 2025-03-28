<div align="center">
  <img width="400" alt="image" src="assets/logo_zheng.png">
  <!-- <br> -->
</div>

<div align="center">

# Aether: Geometric-Aware Unified World Modeling

</div>

<div align="center">
<a href='https://arxiv.org/abs/2503.18945'><img src='https://img.shields.io/badge/arXiv-2503.18945-red'></a> &nbsp;
<a href='https://aether-world.github.io'><img src='https://img.shields.io/badge/Project-Page-Green'></a> &nbsp;
<a href='https://huggingface.co/AetherWorldModel/AetherV1'><img src='https://img.shields.io/badge/Model-Weights-yellow'></a> &nbsp;
<a href=''><img src='https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Demo%20(Coming%20Soon)-blue'></a> &nbsp;
</div>

Aether addresses a fundamental challenge in AI: integrating geometric reconstruction with generative modeling 
for human-like spatial reasoning. Our framework unifies three core capabilities: (1) 🌏 **4D dynamic reconstruction**, 
(2) 🎬 **action-conditioned video prediction**, and (3) 🎯 **goal-conditioned visual planning**. Trained entirely on 
synthetic data, Aether achieves strong zero-shot generalization to real-world scenarios.

<div align="center">
    <img src="assets/teaser.png" alt="Teaser" width="800"/>
</div>

:partying_face: **NEWS**: 

- *Mar. 2025:* AetherV1 is released! Model checkpoints, paper, website, and inference code are all available.


## :hammer: Installation

Note: We recommend using virtual environments such as [Anaconda](https://www.anaconda.com/).

```console
# clone project
git clone https://github.com/OpenRobotLab/Aether.git
cd Aether

# create conda environment
conda create -n aether python=3.10
conda activate aether

# install dependencies
pip install -r requirements.txt
```

## :rocket: Inference

### Run inference demo locally

- 4D reconstruction:
  ```console
  python scripts/demo.py --task reconstruction --video ./assets/example_videos/moviegen.mp4
  ```

- Action-conditioned video prediction:
  ```console
  python scripts/demo.py --task prediction --image ./assets/example_obs/car.png --raymap_action assets/example_raymaps/raymap_forward_right.npy
  ```

- Goal-conditioned visual planning:
  ```console
  python scripts/demo.py --task planning --image ./assets/example_obs_goal/01_obs.png --goal ./assets/example_obs_goal/01_goal.png
  ```

Results will be saved in `./outputs/` by default.

### Run inference demo with Gradio

Coming soon.

## :pencil: Citation
If you find this work useful in your research, please consider citing:

```bibtex
@article{aether,
  title     = {Aether: Geometric-Aware Unified World Modeling},
  author    = {Aether Team and Haoyi Zhu and Yifan Wang and Jianjun Zhou and Wenzheng Chang and Yang Zhou and Zizun Li and Junyi Chen and Chunhua Shen and Jiangmiao Pang and Tong He},
  journal   = {arXiv preprint arXiv:2503.18945},
  year      = {2025}
}
```

## :bulb: Limitations

Aether represents an initial step in our journey, trained entirely on synthetic data. While it demonstrates promising capabilities, it is important to be aware of its current limitations:

- 🔄 Aether struggles with highly dynamic scenarios, such as those involving significant motion or dense crowds.
- 📸 Its camera pose estimation can be less stable in certain conditions.  
- 📐 For visual planning tasks, we recommend keeping the observations and goals relatively close to ensure optimal performance.  

We are actively working on the next generation of Aether and are committed to addressing these limitations in future releases.

## :books: License
This repository is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. For any questions, please email to tonghe90[at]gmail[dot]com.

## :sparkles: Acknowledgements
Our work is primarily built upon 
[Accelerate](https://github.com/huggingface/accelerate), 
[Diffusers](https://github.com/huggingface/diffusers), 
[CogVideoX](https://github.com/THUDM/CogVideo), 
[Finetrainers](https://github.com/a-r-r-o-w/finetrainers), 
[DepthAnyVideo](https://github.com/Nightmare-n/DepthAnyVideo), 
[CUT3R](https://github.com/CUT3R/CUT3R), 
[MonST3R](https://github.com/Junyi42/monst3r), 
[VBench](https://github.com/Vchitect/VBench),
[GST](https://github.com/SOTAMak1r/GST), 
[SPA](https://github.com/HaoyiZhu/SPA), 
[DroidCalib](https://github.com/boschresearch/DroidCalib),
[Grounded-SAM-2](https://github.com/IDEA-Research/Grounded-SAM-2),
[ceres-solver](https://github.com/ceres-solver/ceres-solver), etc.
We extend our gratitude to all these authors for their generously open-sourced code and their significant contributions to the community.
