<h1 align="center">LaGS &amp; SGE</h1>

<p align="center">
  Official implementation of Latent Gaussian Splatting (LaGS) and Streaming Gaussian Encoding (SGE),<br>
  two methods for camera-based 4D panoptic occupancy tracking.
</p>

<p align="center">
  <a href="https://arxiv.org/abs/2602.23172"><img src="https://img.shields.io/badge/arXiv-LaGS%20(2602.23172)-b31b1b.svg" alt="LaGS arXiv"></a>
  <a href="https://arxiv.org/abs/2606.30754"><img src="https://img.shields.io/badge/arXiv-SGE%20(2606.30754)-b31b1b.svg" alt="SGE arXiv"></a>
  <a href="https://lags.cs.uni-freiburg.de/"><img src="https://img.shields.io/badge/Project-LaGS-1f6feb.svg" alt="LaGS project page"></a>
  <a href="https://sge.cs.uni-freiburg.de/"><img src="https://img.shields.io/badge/Project-SGE-1f6feb.svg" alt="SGE project page"></a>
  <img src="https://img.shields.io/badge/python-3.11-blue.svg" alt="Python 3.11">
</p>

<h3 align="center">Latent Gaussian Splatting for 4D Panoptic Occupancy Tracking</h3>
<p align="center">
  <b>IEEE RA-L 2026</b><br>
  Maximilian Luz<sup>1</sup>, Rohit Mohan<sup>1</sup>, Thomas Nürnberg<sup>2</sup>, Yakov Miron<sup>2,3</sup>, Daniele Cattaneo<sup>1</sup>, Abhinav Valada<sup>1</sup><br>
  <a href="https://lags.cs.uni-freiburg.de/">Project Page</a> &nbsp;|&nbsp; <a href="https://arxiv.org/abs/2602.23172">arXiv</a>
</p>

<h3 align="center">Streaming Gaussian Encoding for 4D Panoptic Occupancy Tracking</h3>
<p align="center">
  <b>IEEE/RSJ IROS 2026</b><br>
  Maximilian Luz<sup>1</sup>, Thomas Nürnberg<sup>2</sup>, Yakov Miron<sup>2,3</sup>, Abhinav Valada<sup>1</sup><br>
  <a href="https://sge.cs.uni-freiburg.de/">Project Page</a> &nbsp;|&nbsp; <a href="https://arxiv.org/abs/2606.30754">arXiv</a>
</p>

<p align="center">
  <sup>1</sup> University of Freiburg &nbsp;&nbsp; <sup>2</sup> Bosch Research &nbsp;&nbsp; <sup>3</sup> University of Haifa
</p>

<p align="center">
  <img src="docs/assets/readme/scene_1071_gt_lags_sge.gif" width="95%" alt="GT, LaGS, and SGE qualitative result on nuScenes scene 1071">
  <br>
  <sub>Qualitative nuScenes sequence: ground truth, LaGS, and SGE.</sub>
</p>

## Overview

This repository provides a camera-based framework for **4D panoptic occupancy
tracking** — jointly predicting semantic occupancy and temporally consistent
instance identities from surround-view cameras. It implements two Gaussian-based
models that turn multi-view image observations into compact latent 3D scene
representations before decoding panoptic occupancy and tracks.

### LaGS in Brief

**Latent Gaussian Splatting (LaGS)** revisits 4D panoptic occupancy tracking
through a sparse latent Gaussian scene representation. Multi-view image features
are lifted into 3D, summarized as feature-bearing Gaussian keypoints, processed
with hierarchical point-based attention, and splatted back into a dense voxel
volume for panoptic occupancy decoding. This gives the model adaptive spatial
support and long-range 3D interactions without relying only on dense voxel
operators.

### SGE in Brief

**Streaming Gaussian Encoding (SGE)** extends the Gaussian representation from
LaGS into a persistent streaming scene memory. Instead of rebuilding the
volumetric representation independently at every frame, it propagates latent
Gaussian queries with ego-motion compensation, uses opacity and confidence to
retain well-supported scene structure, and refreshes weak slots with new
observations. This adds representation-level temporal coherence, especially
through occlusion, while staying compatible with the LaGS-style decoder.

---

<p align="center">
  <img src="https://img.shields.io/badge/CODE-COMING%20SOON-f5a623?style=for-the-badge" alt="Code coming soon">
  <br><br>
  The implementation, checkpoints, configurations, and documentation will be released here.
</p>
