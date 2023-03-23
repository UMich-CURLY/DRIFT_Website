---
permalink: /
title: "DRIFT"
excerpt: "About me"
author_profile: true
redirect_from: /sitemap/
---

<p float="middle">Dead Reckoning for Robotics In Field Time (DRIFT): An inEKF-Based Mobile Robot State Estimator Library</p>
<h1 id="h.uigj53erdbnu" dir="ltr" class="zfr3Q duRjpb CDt4Ke " style="background-color: transparent; border-bottom: none; border-left: none; border-right: none; border-top: none; margin-bottom: 0.0pt; margin-top: 0.0pt; padding-bottom: 0.0pt; padding-left: 0.0pt; padding-right: 0.0pt; padding-top: 0.0pt; text-align: center;"><span class="C9DxTc " style="color: #FFFFFF; font-family: Arial; font-size: 12.0pt; font-variant: normal; font-weight: 700; vertical-align: baseline;">Tzu-Yuan Lin &nbsp; &nbsp; &nbsp; Tingjun Li &nbsp; &nbsp; &nbsp; Jonathan Tong &nbsp; &nbsp; &nbsp; Justin Yu</span></h1>
<br>
<p dir="ltr" class="zfr3Q CDt4Ke " style="background-color: transparent; border-bottom: none; border-left: none; border-right: none; border-top: none; margin-bottom: 10.0pt; margin-top: 0.0pt; padding-bottom: 0.0pt; padding-left: 0.0pt; padding-right: 0.0pt; padding-top: 0.0pt; text-align: center;"><span class="C9DxTc " style="font-variant: normal;">University of Michigan, Ann Arbor, MI, USA&nbsp;</span></p>

<p dir="ltr" class="zfr3Q CDt4Ke " style="background-color: transparent; border-bottom: none; border-left: none; border-right: none; border-top: none; margin-bottom: 0.0pt; margin-top: 0.0pt; padding-bottom: 0.0pt; padding-left: 0.0pt; padding-right: 0.0pt; padding-top: 0.0pt; text-align: center;"><span class="C9DxTc " style="font-family: 'Source Code Pro', Arial; font-variant: normal; font-weight: 400;">{tzuyuan,tingjunl,wenzhet,yujustin}@umich.edu</span></p>

<p float="middle">
<div>
    <video autoplay="autoplay" src="./images/town10h_wh_4x.mp4" controls="controls" width="100%" />
</div>
</p>

<div class="page__lead">
    <div class="page__content">
        <div class="HOME-feature-block">
            <div>
                Trace Free Scenes
                <p>
                    <img src="./images/TraceFree.png" alt="Trace Free">
                </p>
                <p>
                    CarlaSC scenes are sampled from multiple viewpoints, ensuring minimal occlusions and no traces left by dynamic objects. The image above showcases MotionSC lack of traces for dynamic objects compared to SemanticKITTI, another well known vision benchmark.
                </p>
            </div>
            <div>
                Sequential Labels
                <p>
                    <img src="./images/SemanticLabel.png" alt="SemanticLabel">
                </p>
                <p>
                    Data is captured at 10Hz and semantic labels along with scene flow data ground truth data is provided for each frame. This provides more information for scene understanding over multiple scans.
                </p>
            </div>
            <div>
                Synthetic Data
                <p>
                    <img src="./images/Carla.png" alt="Carla">
                </p>
                <p>
                    CarlaSC is generated using CARLA, an open source simulator for autonomous driving research. This enables high customizability, from the number of dynamic objects to the position and number of sensors.
                </p>
            </div>
            <!-- <p class="small">
                Additional Information here.
            </p> -->
    </div>

</div>

<div class="page__content">
    Getting started
    <p class="small">
        A description of the dataset and its properties can be found in the <a href="./dataset/">Dataset</a> page on this website. To download it, please visit the <a href="./download/">Download</a> page to download the Cartesian or Cylindrical dataset version. An example of how to use the dataset can be found on the <a href="https://github.com/UMich-CURLY/3DMapping">MotionSC Github</a> repository. This repository contains the CarlaSC dataloader used in the MotionSC paper as well as python visualization scripts.
    </p>
</div>  

<div class="page__content">
    <div>
        Paper
    </div>
    <p class="small">
        See our paper below for more information and our network baseline results: 
        <div>
            <img src="./images/MotionSCPaperAll.png" alt="MotionSC Paper Here" background-size="cover">
        </div>
        <p class="small">
            If you plan to use our dataset and tools in your work, we would appreciate it if you could cite our paper.
            (<a href="https://arxiv.org/abs/2203.07060">PDF</a>)
        </p>
    </p>
</div>  

