---
permalink: /
title: "DRIFT"
excerpt: "Dead Reckoning in Field Time"
author_profile: true
redirect_from: /sitemap/
---

<p style="text-align:center" float="middle"><b style="font-size:15pt">D</b>ead <b style="font-size:15pt">R</b>eckoning <b style="font-size:15pt">I</b>n <b style="font-size:15pt">F</b>ield <b style="font-size:15pt">T</b>ime: A Symmetry-Preserving Filter Based Mobile Robot State Estimator Library</p>
<h1 id="h.uigj53erdbnu" dir="ltr" class="zfr3Q duRjpb CDt4Ke " style="background-color: transparent; border-bottom: none; border-left: none; border-right: none; border-top: none; margin-bottom: 10.0pt; margin-top: 0.0pt; padding-bottom: 0.0pt; padding-left: 0.0pt; padding-right: 0.0pt; padding-top: 0.0pt; text-align: center;"><span class="C9DxTc " style="font-family: Arial; font-size: 12.0pt; font-variant: normal; font-weight: 700; vertical-align: baseline;">Tzu-Yuan Lin &nbsp; &nbsp; &nbsp; Tingjun Li &nbsp; &nbsp; &nbsp; Jonathan Tong &nbsp; &nbsp; &nbsp; Justin Yu &nbsp; &nbsp; &nbsp; Maani Ghaffari</span></h1>

<p dir="ltr" class="zfr3Q CDt4Ke " style="background-color: transparent; border-bottom: none; border-left: none; border-right: none; border-top: none; margin-bottom: 10.0pt; margin-top: 0.0pt; padding-bottom: 0.0pt; padding-left: 0.0pt; padding-right: 0.0pt; padding-top: 0.0pt; text-align: center;"><span class="C9DxTc " style="font-variant: normal;">University of Michigan, Ann Arbor, MI, USA&nbsp;</span></p>

<p float="middle">
<div>
    <!-- <video style="border-radius:15px" controls muted autoplay="autoplay" src="./images/placeholder.mp4" controls="controls" width="100%" /> -->
    <!-- <script>
    document.getElementById('vid').play();
    </script> -->
    <iframe width="560" height="315" src="https://www.youtube.com/embed/73HMagemIng?si=_NK84zxx0eMYDH13" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
    <!--<iframe style="width:100%" src=" https://www.youtube.com/embed/oVbP-Y8xT_E?autoplay=1" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen="false" id="fitvid0"></iframe>-->
</div>
</p>
<div class="page__lead">
    <div class="page__content">
    <b>Overview</b>
        <div>
            <p class="small">
Dead Reckoning In Field Time (DRIFT) is an open-source C++ software library designed to provide accurate and high-frequency state estimation for a variety of mobile robot architectures, including legged, wheeled, and marine platforms. Leveraging symmetry-preserving filters such as Invariant extended Kalman filtering (InEKF), this modular library empowers roboticists and engineers with a robust and adaptable tool to estimate instantaneous local pose and velocity in diverse environments. The software is structured in a modular fashion, allowing users to define their own sensor types, and propagation and correction methods, offering a high degree of customization.

<br>
<br>

As a header-only library, DRIFT aims to make real-time robot localization easy and accessible, promoting seamless integration across numerous platforms. Additionally, we provide support for ROS middleware interface. In the future, we plan to expand support for both Lightweight Communications and Marshalling (LCM) and ROS 2.
            </p>
            <div align="center"><img src="./images/flow_chart.jpg" alt="HighLevelFlow" style="max-width:120%;height:auto"></div>
        </div>
    </div>
</div>

<div class="page__lead">
    <div class="page__content">
    <b>Tested Platforms</b>
        <div class="HOME-feature-block">
            <div>
                Husky
                <p>
                   <a href="https://clearpathrobotics.com/husky-unmanned-ground-vehicle-robot/" target="_blank"><img src="./images/husky.png" alt="Husky" style="border-radius:10px"></a>
                </p>
                <!--<p>
                    The Husky robot is a wheeled mobile robot platform designed and manufactured by Clearpath Robotics, a Canadian robotics company.
                </p>-->
            </div>
            <div>
                MIT MiniCheetah
                <p>
                    <a href="https://www.naverlabs.com/mini-cheetah" target="_blank"><img src="./images/minicheetah_forest.jpg" alt="MITMiniCheetah" style="border-radius:10px"></a>
                </p>
                <!--<p>
                    The MIT MiniCheetah is a quadrupedal robot designed and developed by the Massachusetts Institute of Technology's Biomimetic Robotics Laboratory.
                </p>-->
            </div>
            <div>
                Fetch
                <p>
                    <a href="https://fetchrobotics.com/" target="_blank"><img src="./images/fetch.jpg" alt="fetch" style="border-radius:10px"></a>
                </p>
                <!--<p>
                    The Unitree Go1 is a quadruped robot designed and manufactured by Unitree Robotics.
                </p>-->
            </div>
            <div>
                MRZR-D4
                <p>
                    <a href="https://military.polaris.com/en-us/mrzr/" target="_blank"><img src="./images/MRZR_D4.png" alt="MRZR" style="border-radius:10px"></a>
                </p>
                <!--<p>
                    The Unitree Go1 is a quadruped robot designed and manufactured by Unitree Robotics.
                </p>-->
            </div>
            <div>
                Girona 500 AUV (Simulation)
                <p>
                    <a href="https://iquarobotics.com/girona-500-auv" target="_blank"><img src="./images/stonefish.png" alt="MRZR" style="border-radius:10px"></a>
                </p>
                <!--<p>
                    The Unitree Go1 is a quadruped robot designed and manufactured by Unitree Robotics.
                </p>-->
            </div>
            <!-- <p class="small">
                Additional Information here.
            </p> -->
    </div>

</div>
<br>
<div class="page__content">
    <b>Getting Started</b>
    <p class="small">
        Head to our <a href="https://umich-curly.github.io/DRIFT_Website/tutorials/" target="_blank">Getting Started</a> tutorial page.
        Code for this project can be found in the <a href="https://github.com/UMich-CURLY/curly_state_estimator"> Github</a> repository.
    </p>
</div>  

<!--
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
-->

<div class="page__content">
    <b>Citation</b><br>
<p class="small">
        If you use this work or find it helpful, please consider citing: (bibtex)

<br><br>Tzu-Yuan Lin, Tingjun Li, Wenzhe Tong, and Maani Ghaffari. "Proprioceptive Invariant Robot State Estimation." arXiv preprint arXiv:2311.04320 (2023). (Under review for Transaction on Robotics)<br>
    </p>
<pre>
  <code>
@article{lin2023proprioceptive,
  title={Proprioceptive Invariant Robot State Estimation},
  author={Lin, Tzu-Yuan and Li, Tingjun and Tong, Wenzhe and Ghaffari, Maani},
  journal={arXiv preprint arXiv:2311.04320},
  year={2023}
}
</code>
</pre>
<p class="small">
<br><br>Tzu-Yuan Lin, Ray Zhang, Justin Yu, and Maani Ghaffari. "Legged Robot State Estimation using Invariant Kalman Filtering and Learned Contact Events." In Conference on Robot Learning. PMLR, 2021<br>
    </p>
<pre>
  <code>
@inproceedings{
   lin2021legged,
   title={Legged Robot State Estimation using Invariant Kalman Filtering and Learned Contact Events},
   author={Tzu-Yuan Lin and Ray Zhang and Justin Yu and Maani Ghaffari},
   booktitle={5th Annual Conference on Robot Learning },
   year={2021},
   url={https://openreview.net/forum?id=yt3tDB67lc5}
}
  </code>
</pre>
</div>  