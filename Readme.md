# Real-Time Object-Aware Distance Estimation

[![License](https://img.shields.io/badge/license-MIT-green)](#license)

## Project Overview

This project demonstrates a real-time computer vision pipeline for estimating
relative object distance by integrating YOLO-based object detection with
monocular depth prediction using MiDaS with a DPT-Large backbone.

The system operates on a single RGB video stream and produces object-level
depth-aware distance cues in real time.

---

## Table of Contents

- [Project Overview](#project-overview)
- [System Overview](#system-overview)
- [Key Components](#key-components)
- [Demo](#demo)
- [Learning Outcomes](#learning-outcomes)
- [Limitations](#limitations)
- [License](#license)

---

## System Overview

The pipeline consists of the following stages:

1. **Object Detection**
   - YOLOv8 is used to detect and localize objects in each video frame.

   - Custom object annotations were prepared using Roboflow for dataset management
     and labeling.

2. **Monocular Depth Estimation**
   - MiDaS predicts a dense depth map from the same RGB frame.
   - The depth map represents *relative scene depth* rather than absolute metric distance.

3. **Object-Level Distance Inference**
   - Depth values are aggregated from the predicted depth map within each detected
     object’s bounding box.
   - These values are used to infer **relative distance cues** for detected objects.

---

## Key Components

- Object Detection: YOLO
- Depth Estimation: MiDaS (monocular, relative depth)
- Input: RGB video or live camera stream
- Output: Object bounding boxes with depth-based distance indication

---

## Demo

A demo video illustrating real-time object-aware distance estimation is provided:

- `car_output.mp4`  

---

## Learning Outcomes

Through this project, I gained hands-on experience in:

- Integrating object detection and monocular depth estimation into a unified
  real-time vision pipeline
- Interpreting dense depth maps and deriving object-level distance cues
- Understanding the limitations of monocular depth estimation, particularly
  scale ambiguity and scene dependency
- Designing inference-focused systems under real-time performance constraints
- Debugging and evaluating vision pipelines in unconstrained outdoor environments

---

## Limitations

- Monocular depth estimation cannot recover absolute scale without additional
  calibration or multi-view information.
- Performance may degrade under extreme lighting conditions, motion blur,
  or heavy occlusion.

---

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/MinhazAyon/vehicle-distance-estimation/blob/main/LICENSE) file for details.

---

## Contact

- **Author:** Minhaz Uddin  
- **Email:** minhaz182219@gmail.com  
- **GitHub:** [github.com/MinhazAyon](https://github.com/MinhazAyon)
- **Whatsapp:** 01628182219
