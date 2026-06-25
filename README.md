Early Glaucoma Detection Using Multimodal Analysis of Fundus Images

This repository contains the implementation of a multimodal deep learning framework for early glaucoma detection using retinal fundus images. The proposed architecture combines structural information from the optic nerve head region and vascular characteristics extracted from retinal blood vessels to improve glaucoma screening performance.

Dataset

The study utilizes data from the Standardized Multi-Channel Dataset for Glaucoma (SMDG-19), which provides standardized fundus images and associated annotations for glaucoma-related tasks. Specifically, two subsets are used:

FIVES: Fundus Image Vessel Segmentation dataset for retinal blood vessel segmentation.
REFUGE1: Retinal Fundus Glaucoma Challenge dataset for optic disc and optic cup segmentation and glaucoma assessment.

Dataset download: https://www.kaggle.com/datasets/deathtrooper/multichannel-glaucoma-benchmark-dataset

SMDG-19 Dataset: Kaggle SMDG-19 Dataset
Project Pipeline
1. Data Preparation
Fundus image preprocessing
Image resizing and normalization
Dataset organization for segmentation and classification tasks
Preparation of vessel, optic disc, and optic cup annotations
2. Blood Vessel Segmentation Training

A U-Net model is trained using the FIVES dataset to learn retinal blood vessel segmentation and vascular structure extraction.

3. Blood Vessel Segmentation on REFUGE1

The trained vessel segmentation model is applied to REFUGE1 fundus images to generate retinal vessel masks for subsequent feature extraction.

4. Optic Disc and Optic Cup Segmentation

Optic disc (OD) and optic cup (OC) structures are segmented from fundus images using a U-Net-based architecture with EfficientNet-B4 encoder. The resulting segmentation masks are used to compute glaucoma-related structural biomarkers.

5. Feature Extraction

Features are extracted from both anatomical and vascular structures, including:

Cup-to-Disc Ratio (CDR)
Vessel Density

These features represent complementary indicators associated with glaucomatous changes.

6. Fusion-Based Classification

A multimodal fusion classifier combines CDR and vessel density features to perform glaucoma classification and identify glaucoma-suspect cases from retinal fundus images.

Repository Structure
data_preparation/ – Data preprocessing and dataset preparation scripts
vessel_segmentation/ – Blood vessel segmentation training and inference
od_oc_segmentation/ – Optic disc and optic cup segmentation models
feature_extraction/ – CDR and vessel density computation
classification/ – Fusion-based glaucoma classification
notebooks/ – Google Colab notebooks and experiments
Objective

The primary objective of this project is to develop an automated framework for early glaucoma detection by integrating optic nerve head morphology and retinal vascular information through multimodal analysis of fundus image
