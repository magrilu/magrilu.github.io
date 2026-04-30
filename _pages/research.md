---
layout: page
title: research
permalink: /research/
description: Geometry-driven computer vision for estimation and reconstruction under non-ideal conditions.
nav: false
nav_order: 2
---

I work in **Computer Vision**, focusing on geometry-driven methods for estimation and 3D reconstruction under non-ideal conditions.

My research deals with settings where standard assumptions break: data may contain multiple structures, measurements may include outliers, reconstruction may become ambiguous, and sensing conditions may be heterogeneous or unconventional.


- [**Robust fitting and multi-structure estimation**](#robust-fitting)  
  Methods for recovering multiple parametric models from noisy data with outliers and overlapping structures.

- [**Calibration and 3D reconstruction**](#calibration)  
  Problems in multiview geometry arising when camera parameters are unknown, scenes are dynamic or sensing modalities are heterogeneous.

- [**Critical configurations in 3D reconstruction**](#critical-configurations)  
  When and why does 3D reconstruction fail?

- [**Structure-based anomaly detection**](#anomaly-detection)  
  When the main interest is not modeling the underlying structures, but detecting the observations that do not conform to them.



Jump to: [Robust fitting](#robust-fitting) · [Calibration](#calibration) · [Critical configurations](#critical-configurations) · [Anomaly detection](#anomaly-detection)

---

## Robust fitting and multi-structure estimation

Methods for estimating multiple geometric models from noisy data with outliers and overlapping structures.

**Clustering of preferences.**  
A recurring idea in this line of work is to represent data through the preferences they grant to a pool of provisional models. This turns multi-model fitting into a clustering problem in a suitable conceptual space, as in T-Linkage {% cite 2014_cvpr %}, Multi-Link {% cite magri2021 %}, and robust matrix-factorization approaches {% cite 2015_bmvc magri2017multiple %}.

**Coverage formulations.**  
An alternative view formulates multi-model fitting as a coverage problem, yielding a simple and principled alternative to clustering-based methods {% cite 2016_cvpr %}. This perspective also motivates later work on quantum optimization formulations {% cite FarinaAl23 %}.

**Applications.**  
These methods have been applied to indoor point clouds for scan2BIM {% cite 2018_3dv 2019_ispr %}, motion segmentation, and 1D signal analysis in industrial settings.

## Calibration and geometric reconstruction

Methods for calibration and reconstruction in multiview geometry, from minimal problems to modern sensing systems.

**Autocalibration and camera models.**  
This includes work on minimal autocalibration problems, self-calibration in dynamic scenes, and flexible models for wide-angle cameras.

**Multimodal and dynamic reconstruction.**  
A second line addresses calibration and reconstruction with heterogeneous sensor suites and scenes containing multiple rigid motions, combining geometric reasoning with learning-based components.

## Critical configurations in 3D reconstruction

A more theoretical line of work studies when and why reconstruction becomes ambiguous or unstable.

Using tools from algebraic geometry, this research analyzes **critical configurations**: situations in which different 3D scenes or camera arrangements produce indistinguishable image observations {% cite bertolini2020critical bertolini2019critical %}. The goal is to better understand the failure modes of reconstruction pipelines.

## Structure-based anomaly detection

This line of work studies how to detect observations that do not conform to an underlying geometric or structural pattern.

Instead of recovering all structures first and labeling the residual points as outliers, these methods aim to identify anomalies directly through preference embeddings and isolation mechanisms {% cite leveni2020 LeveniAl23 RizzoAl23 %}. Applications range from geometric data to industrial monitoring and optical sensing.

---
I work in **Computer Vision**, focusing on geometry-driven methods for estimation and 3D reconstruction in non-ideal conditions.
My research addresses scenarios where standard assumptions break: data may contain multiple structures, measurements may be corrupted by outliers, reconstruction may be ambiguous, and sensing conditions may be heterogeneous or unconventional.

Below is an overview of the main research directions, with some representative papers.

## Robust fitting and multi-structure estimation

Estimating geometric models in the presence of outliers and multiple structures is a fundamental challenge in Computer Vision. Rather than assuming that the data can be explained by a single model, this line of research addresses settings where several geometric structures may coexist and need to be recovered jointly from noisy observations.

**Clustering of preferences.**  
A recurring idea in this line of work is to represent data through the preferences they grant to a pool of provisional models generated by random sampling. Within this perspective, multi-model fitting becomes a clustering problem in a suitable conceptual space. T-Linkage {% cite 2014_cvpr %}, and Multi-Link {% cite magri2021 %} approach multi-model fitting from this viewpoint, resulting in practical—albeit greedy—methods that provide a hierarchical interpretation of the data and can also handle heterogeneous model classes. When the number of structures is known, robust matrix factorization can instead be used to reduce multi-model fitting to a collection of easier robust estimation problems {% cite 2015_bmvc magri2017multiple %}.

**Coverage formulations.**  
A different direction consists in formulating multi-model fitting as a coverage problem, yielding RansaCov {% cite 2016_cvpr %} a simple and principled alternative to clustering-based approaches. In this view, the goal is to select a set of models that jointly explains the data while naturally accounting for outliers and intersecting structures. This formulation was later extended to quantum optimization hardware, connecting robust estimation with emerging computational paradigms that are well suited to the combinatorial nature of the problem {% cite FarinaAl23 pandey2025outlier%}.

**Applications.**  
These methods have been applied in different domains, including indoor point clouds for scan2BIM {% cite 2018_3dv 2019_ispr %}, motion segmentation {% cite %}, and geometric primitive decomposition with superquadrics {% cite ferraris2025geometric%} in the context of the **GEOPRIDE** project (PRIN).




## Calibration and geometric reconstruction

Another research direction concerns calibration and reconstruction problems in multiview geometry, ranging from foundational questions to methods for modern sensing systems.

On the theoretical side, this includes work on minimal problems and autocalibration. On the applied side, it includes calibration methods for wide-angle cameras, multimodal sensor suites, and dynamic scenes, as well as reconstruction pipelines that combine geometric reasoning with learning-based components.

**Selected papers**

**Minimal Perspective Autocalibration**  
  Introduces a new family of minimal autocalibration problems and practical solvers for recovering camera intrinsics from point correspondences. {% cite cin2024minimal%}

**Revisiting Calibration of Wide-Angle Radially Symmetric Cameras**  
  Proposes a two-step framework that separates an implicit camera representation from the final parametric model, improving flexibility in wide-angle calibration. {% cite cin2024revisiting%}

**Multi-body Self-Calibration**  
  Shows how multiple independently moving rigid bodies can provide useful constraints for self-calibration, rather than being treated only as a nuisance. {% cite dalcin2022 %}

**One Target to Align Them All: LiDAR, RGB and Event Cameras Extrinsic Calibration**  
  Presents a joint calibration framework for heterogeneous sensor suites, with particular attention to the challenges posed by event cameras. {% cite bertogalli2025targetalignalllidar %}

**Multi-body Depth and Camera Pose Estimation from Multiple Views**  
  Addresses depth and pose estimation in dynamic scenes with multiple rigid motions, overcoming scale inconsistencies typical of multi-body reconstruction. {% cite CinAl23 %}

**Principled Bundle Block Adjustment with Multi-Head Cameras**  
  Studies constrained bundle adjustment for multi-camera systems, with an emphasis on relative orientation constraints and rigorous geometric modeling. {% cite MASET2023100051 maset2020 %}
  
## Critical configurations in 3D reconstruction

When and why does 3D reconstruction fail?
Using tools from algebraic geometry, this research analyzes **critical configurations**: situations in which different 3D scenes or camera arrangements produce indistinguishable image observations. Understanding these degeneracies is important both from a theoretical point of view and for designing reconstruction pipelines that are aware of their own failure modes.

**Selected papers**

**Critical Hypersurfaces and Instability for Reconstruction of Scenes in High Dimensional Projective Spaces**  
  Studies critical loci for reconstruction in higher-dimensional projective settings and analyzes the instability phenomena arising near them. {% cite bertolini2020critical %}

**Critical Loci for Two Views Reconstruction as Quadratic Transformations Between Images**  
  Describes the effect of critical configurations directly on the image planes, linking them through quadratic transformations. {% cite bertolini2019critical %}

## Structure-based anomaly detection

In several applications, the goal is not only to model structure, but also to identify observations that do not conform to it.

This line of work can be seen as complementary to multi-model fitting: instead of first recovering all structures and then labeling the residual points as outliers, it focuses on directly detecting anomalies as deviations from geometric or structural patterns.

Applications range from geometric data to industrial monitoring and optical sensing.

**Selected papers**

**PIF: Anomaly Detection via Preference Embedding**  
  Introduces an anomaly detection framework based on preference embeddings, where anomalies emerge as isolated points with respect to underlying geometric structure. {% cite leveni2020 %}

**Hashing for Structure-Based Anomaly Detection**  
  Improves the efficiency of structure-based anomaly detection by using hashing techniques to avoid explicit distance computations in high-dimensional preference spaces. {% cite LeveniAl23 %}

**Anomaly Detection in Optical Spectra via Joint Optimization**  
  Applies structure-aware anomaly detection ideas to optical spectra, showing how trend and structure estimation can support industrial monitoring. {% cite RizzoAl23 %}

## Applications

These methods have been explored across several domains, including **3D reconstruction**, **motion segmentation**, **scan2BIM**, **optical sensing and industrial monitoring**, and **multimodal perception**.