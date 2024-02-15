---
title: "Online quality assessment of human movements from Kinect skeleton data"
collection: research_medical_past
permalink: /research_medical_past/movement_quality
---

2013-2016

Summary 
======

The objective of this project is to evaluate the quality of human movements from visual information which has use in a broad range of
applications, from diagnosis and rehabilitation to movement optimisation in sports science. Observed movements are compared with a model
of normal movement and the amount of deviation from normality is quantified automatically.

## Description of the proposed method

The figure below illustrates the pipeline of our proposed method.

![Pipeline of the proposed method](overview-600x145.png)

### Skeleton extraction

We use a Kinect camera, that measures distances and provides a depth map of the scene instead of the classic RGB image.
A skeleton tracker [1] can use this depth map to fit a skeleton on the person being filmed. We then normalise the skeleton to compensate
for people having various heights. This normalised skeleton is the basis of our movement analysis technique.

### Robust dimensionality reduction

A skeleton contains 15 joints, forming a vector of 45 coordinates. Such vector has a quite high dimensionality but also redundant
information. We use a manifold learning method, Diffusion Maps [2], to reduce the dimensionality and extract the significant information
from this skeleton.

Skeletons extracted from depth maps tend to suffer from a high amount of noise and outliers. Therefore, we modify the original Diffusion
Maps [2] to add the extension that Gerber et al. [3] proposed for dealing with outliers in Laplacian Eigenmaps that are another type of
manifold.

Our manifold provides us with a new representation $\mathbf{Y}$ of the pose, derived from the normalised skeleton, with a much lower
dimensionality (typically 3 dimensions instead of the initial 45) and significantly less noise and outliers. We use this new pose feature
$\mathbf{Y}$ to assess the quality of the movement.

### Assessment against a statistical model of normal movement

We build two statistical models from our new pose feature, which describe respectively normal *poses* and normal *dynamics*. These models
are represented by probability density functions (pdf) which are learnt, using Parzen window estimators, from training sequences that
contain only normal instances of the movement.

The pose model is in the form of the pdf $f_{Y}\left(y\right)$ of a random variable $Y$ that takes as value $y=\mathbf{Y}$ our pose feature
vector $\mathbf{Y}$. The quality of a new pose $y_t$ at frame $t$ is then assessed as the log-likelihood of being described by the pose
model, i.e. $$\mbox{llh}_{\mbox{pose}}= \log f_{Y}\left(y_t\right) \; .$$

The dynamics model is represented as the pdf $f_{Y_t}\left(y_t|y_1,\ldots,y_{t-1}\right)$ which describes the likelihood of a pose $y_t$
at a new frame $t$ given the poses at the previous frames. In order to compute it, we introduce $X_t$ with value
$x_t \in \left[0,1\right]$, which is the stage of the (periodic or non-periodic) movement at frame $t$. Note, in the case of periodic
movements, this movement stage can also be seen as the phase of the movement’s cycle. Based on Markovian assumptions, we find that
$$ f_{Y_t}\left(y_t|y_1,\ldots,y_{t-1}\right) \approx f_{Y_t}\left(y_t|\hat{x}_t\right) f_{X_t}\left(\hat{x}_t|\hat{x}_{t-1}\right) \; ,$$
with $\hat{x}_t$ an approximation of $x_t$ that minimises $f_{\left\{X_0,\ldots,X_t\right\}}\left(x_0,\ldots,x_t|y_1,\ldots,y_t\right)$.
$f_{Y_t}\left(y_t|x_t\right)$ is learnt from training sequences using Parzen window estimation, while $f_{X_t}\left(x_t|x_{t-1}\right)$
is set analytically so that $x_t$ evolves steadily during a movement. The dynamics quality is then assessed as the log-likelihood of the
model describing a sequence of poses within a window of size $\omega$:
$$\mbox{llh}_{\mbox{dyn}} \approx \frac{1}{\omega} \sum_{i=t-\omega+1}^{t} \log\left( f_{Y_i}\left(y_i|x_i\right) f_{X_i}\left(x_i|x_{i-1}\right) \right)\; .$$

Two thresholds on the two likelihoods, determined empirically, are used to classify the gait being normal and abnormal.
Thresholds on the derivatives of the log-likelihoods allow refining the detections of abnormalities and of returns to normal.

**Role in the project:**  Post-doctoral researcher

**Paper:** [Download here](mémoire_thèse-min.pdf)

**Code:** [Download here](iresisd-1.6.zip)
