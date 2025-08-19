# Drone-based Biological Pest Control in High Tunnels
Drone-based Biological Pest Control in High Tunnels


## 0. Preface

- This repository includes detailed introduction, data and source code for drone navigation. If you have any questions about our project, feel free to contact [M. Khalid Jawed](https://structures.computer/) or [Tuan-Anh Vu](mailto:tuananh1007@ucla.edu) via E-mail. 

### 0.1. :fire: NEWS :fire:
- [2025/04/15] :boom: **Our project page is live**, we will periodically update more information.
<!-- - [2025/04/15] Training/Testing code will be updated soon ...
- [2025/04/15] Data will be release soon ... -->

### 0.2. Table of Contents

- [Drone Navigation](#drone-based-biological-pest-control-in-high-tunnels)
  - [0. Preface](#0-preface)
    - [0.1. :fire: NEWS :fire:](#01-fire-news-fire)
    - [0.2. Table of Contents](#02-table-of-contents)
  - [1. Overview](#1-Overview)
  - [2. Usage](#2-usage)
  - [3. Results](#3-results)
    - [3.1. Qualitative Comparison](#31-qualitative-comparison)
    - [3.2. Quantitative Comparison](#32-quantitative-comparison)
  - [4. Citation](#4-citation)
  - [5. LICENSE](#5-license)
  - [6. Acknowledgements](#6-acknowledgements)
  - [7. TODO LIST](#7-todo-list)


## 1. Overview

<p align="center">
    <img src="./files/teaser.png"/> <br />
    <em> 
    Figure 1: Our deployed AI model on drone can identify obstacles, 
    rows of crops, and entry/exit points of tunnels and navigate them autonomously.
    </em>
</p>

Drone-based release of biocontrol organisms is an emerging method of conducting high-throughput biocontrol in a variety of California crops that reduces the use of traditional pesticides. Drones offer an economically feasible alternative to hand release of biocontrol organisms that enables more precise, targeted, and frequent applications. While this approach is currently largely limited to agricultural fields, the technology offers advantages in unique environments. High tunnels offer an economical means of protected cultivation, safeguarding crops from adverse weather conditions and extending the production season. Despite these advantages, pest management poses a more significant challenge compared to open fields. Common economically-important pests in high tunnels include two-spotted spider mites, whiteflies, and thrips. In addition, maneuvering in these environments is more challenging than in open air due to obstacles, a lack of reliable Global Positioning System (GPS) signals within the tunnels, cramped spaces with limited maneuverability, and the construction of many high tunnels on hilly or uneven terrain, which can further complicate drone operations and navigation within the tunnels. 

To address these technical challenges, the project will develop software that relies on computer vision and artificial intelligence (AI) which will allow the software to function without a GPS signal. After collecting and annotating a dataset of photos and videos of high tunnels, an AI model will be trained that can identify obstacles, rows of crops, and entry/exit points of tunnels and navigate them autonomously. Flight performance will be evaluated, first in a controlled environment and next in real-world fields. Small-scale tests will be conducted in year three of the project to compare pest counts among multiple strawberry tunnels in hand-release and drone-treated approaches. 

In concert with pest control advisers, integrated pest management experts, and growers, a cost comparison of conventional pesticide, hand-released biocontrol, and drone-based biocontrol will be conducted. This comparison will include analysis of crop losses due to ineffective pesticide application, environmental and health costs, and resistance management costs. To ensure economic viability, development will focus on a low- cost solution so that the price of biocontrol is competitive between field production and high tunnels. 

This project contributes to DPR's mission to protect human health and the environment, and supports California's transition to safer, more sustainable pest management, by developing and testing drone-based biocontrol, potentially supporting the future expansion of biocontrol of pests in high tunnels, an important California cropping setting. Biocontrol can be an effective replacement for the use of traditional pesticides, and the project will provide actionable data on economic sustainability of the approach.

## 2. Usage

The training and testing experiments are conducted using [PyTorch](https://github.com/pytorch/pytorch) with 
a single GeForce RTX A6000 GPU of 48 GB Memory.

> Note that our model also supports low memory GPU, which means you can lower the batch size


1. Configuring your environment (Prerequisites):
   
    Note that our model is only tested on Ubuntu OS with the following environments. 
    It may work on other operating systems as well but we do not guarantee that it will.
    
    + Creating a virtual environment in terminal: `conda create -n drone python=3.9`.
    
    + Installing necessary packages: `pip install -r requirements.txt`.
    
    + (Optional: only for training) Installing [NVIDIA-Apex](https://github.com/NVIDIA/apex) 
    for accelerate training process with mixed precision. 
    [(Instructions)](https://github.com/NVIDIA/apex#linux) (Under CUDA-xx.x and Cudnn-x.x).

<!--2. Downloading Testing Sets: -->
2. Downloading Training and Testing Sets:
    + downloading **_NEW testing dataset_** (xxx) and move it into `./Dataset/TestDataset/`, 
    which can be found in this [Google Drive link](https://drive.google.com/file/d/).
    
    + download **_NEW training dataset_** (xxx) which can be found in this [Google Drive link](https://drive.google.com/file/d/).
    + <a href="https://github.com/EvelynZhu88/DroneNav_dataset.git">📥 Download our dataset here </a>.
    

3. Testing Configuration:

    + After you download all the pre-trained model and testing data, just run `test.py` to generate the final prediction map: 
    replace your trained model directory (`--model_path`) and assign your the save directory of the inferred mask (`--test_save`)
    
    + Note that we can use a mixed training strategy of Apex lib (`mode=O1`) and get better performance. 

4. Evaluation your trained model:

    + Run `eval.py` to generate the evaluation results in `./Results/`.

## 3. Results

### 3.1. Qualitative Comparison
<!-- <p align="center">
    <img src="./files/qualitative.png"/> <br />
    <em> 
    Figure 2: Qualitative results of our proposed method and other methods.
    </em>
</p> -->

### 3.2. Quantitative Comparison

<!-- <p align="center">
    <img src="./files/quantitative.png"/> <br />
    <em> 
    Table 1: Quantitative results on different datasets. The best scores are highlighted in bold.
    </em>
</p> -->


## 4. Citation

Please cite our paper if you find the work useful: 

	@inproceedings{xxx,
  	title={Drone Navigation },
  	author={xxx},
  	booktitle={xxx},
  	year={2025}
	}

## 5. LICENSE

- Our XXX dataset is made available for non-commercial purposes only.

- You will not, directly or indirectly, reproduce, use, or convey the XXX Dataset 
or any Content, or any work product or data derived therefrom, for commercial purposes.

This code is for academic communication only and not for commercial purposes. 
If you want to use for commercial please contact me.

Redistribution and use in source with or without
modification, are permitted provided that the following conditions are
met:

* Redistributions of source code must retain the above copyright
  notice, this list of conditions and the following disclaimer.
  
* Redistributions in binary form must reproduce the above copyright
  notice, this list of conditions and the following disclaimer in
  the documentation and/or other materials provided with the distribution

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE 	
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.

## 6. Acknowledgements

This project was funded by the Department of Pesticide Regulation. The contents may not necessarily reflect the official views or policies of the State of California.

## 7. TODO LIST

- [ ] Support `NVIDIA APEX` training.

- [ ] Support different backbones (VGGNet, ResNet, etc.)

- [ ] Support distributed training.

- [ ] Support lightweight architecture and real-time inference, like MobileNet, SqueezeNet.

- [ ] Add more comprehensive competitors.
    
---

**[⬆ back to top](#0-preface)**
