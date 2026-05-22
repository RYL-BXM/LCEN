LCEN: Lightweight End-to-End Weakly Supervised Semantic Segmentation via Completeness Enhancement with Noise Suppression

This code repository is associated with the paper "LCEN: Lightweight End-to-End Weakly Supervised Semantic Segmentation via Completeness Enhancement with Noise Suppression", which is currently under review at Pattern Analysis and Applications. Please cite our submitted paper if you use this code for your research.

1. Project Introduction
Weakly Supervised Semantic Segmentation (WSSS) realizes pixel-level segmentation with only image-level labels, greatly reducing annotation costs. However, existing end-to-end WSSS methods based on frozen CLIP still face two key problems: incomplete object activation and serious background false activation, which seriously affect the quality of pseudo-labels.

To solve these problems, we propose a lightweight end-to-end framework called LCEN. The framework contains two innovative modules: Dual-Channel Contextual Modulation (DCCM) and Hybrid Channel-Spatial Attention (HCSA). DCCM enhances incomplete regions and object boundaries. HCSA suppresses background noise and semantic interference.

Extensive experiments on PASCAL VOC 2012 and MS COCO 2014 prove that LCEN achieves state-of-the-art performance with low computational cost.

2. Software Dependencies
All required packages are listed in requirements.txt.

Install command:
pip install -r requirements.txt

3. Dataset Preparation
Our experiments are conducted on two standard benchmarks: PASCAL VOC 2012 and MS COCO 2014.

Dataset Download Links:
- PASCAL VOC 2012: http://host.robots.ox.ac.uk/pascal/VOC/
- SBD Dataset: http://home.bharathh.info/pubs/codes/SBD/download.html
- MS COCO 2014: https://cocodataset.org/

Place datasets in the following structure:
datasets/
├── VOC2012/
├── SBD/
└── COCO2014/

Please modify the dataset path to your local absolute path before training.

4. Model Training
Train on PASCAL VOC 2012:
python dist_clip_voc.py

Train on MS COCO 2014:
python dist_clip_coco.py

Trained weights are saved in checkpoints/. Training logs are stored in logs/.

5. Model Validation & Evaluation
Evaluate on PASCAL VOC 2012:
python eval_voc.py

Evaluate on MS COCO 2014:
python eval_coco.py

Multi-scale flip test:
python test_msc_flip_voc.py
python test_msc_flip_coco.py

CAM visualization:
python vis_cam_from_npy.py
python vis_coco_cam_from_npy.py

All results are saved in results/.

6. Experimental Results
PASCAL VOC 2012
Method	Backbone	Val mIoU	Test mIoU
WeCLIP	ViT-B	76.4	77.2
ExCEL	ViT-B	78.4	78.5
LCEN (Ours)	ViT-B	81.2	83.3

MS COCO 2014
Method	Backbone	mIoU
WeCLIP	ViT-B	47.1
ExCEL	ViT-B	50.3
LCEN (Ours)	ViT-B	53.2

7. Visualization
Framework Overview

PASCAL VOC 2012 Results

MS COCO 2014 Results

8. Repository Structure
LCEN-RYL/
├── WeCLIP_Plus/
├── generate_cams_coco14.py
├── generate_cams_voc12.py
├── test_msc_flip_coco.py
├── test_msc_flip_voc.py
├── test_msc_flip_seg.py
├── vis_cam_from_npy.py
├── vis_coco_cam_from_npy.py
├── dist_clip_voc.py
├── dist_clip_coco.py
├── eval_voc.py
├── eval_coco.py
├── requirements.txt
└── README.md

9. Citation
@article{ren2026lcen,
  title={LCEN: Lightweight End-to-End Weakly Supervised Semantic Segmentation via Completeness Enhancement with Noise Suppression},
  author={Ren, YiLong and Zhao, XueZhuan and Li, LingLing and Shao, XiaoYan and Ren, Ning and Zhang, Jian},
  journal={Pattern Analysis and Applications},
  year={2026}
}

10. Contact
Email: renyilong2026@163.com

11. License
This project is released under the MIT License.
