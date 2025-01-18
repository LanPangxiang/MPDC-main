# MPDC：Multi-Perspective Modeling and Diffusion-Based Contrastive Learning for Next POI Recommendation
![overall](https://github.com/user-attachments/assets/8a48ea1c-3b9b-45e0-8be2-6a0172ff5ebd)
This paper proposes a novel next POI recommendation method (**MPDC**) that leverages multi-perspective modeling of visit factors and diffusion-based contrastive learning. We mitigate non-subjective visit factors by leveraging bidirectional information from user sequences and designing a preference filter. Meanwhile, we integrate spatio-temporal information and build a spatial-aware hyperbolic graph module to consider users' subjective visit factors. Based on the generation capability of diffusion models, we develop a diffusion-based preference contrast module that generates latent ideal location preferences for users under different context conditions guided through a diffusion model. 

## ![08C9DD45](https://github.com/user-attachments/assets/818a9e82-4e2f-41d4-9114-d4b40d234748) Environment
    pip install python==3.11.4
    pip install torch-geometric == 2.5.3
    pip install numpy==1.24.0
    pip install pytorch ==2.0.1
    pip install scipy==1.11.2

Please refer to the **requirements.txt** for specific environmental requirements

## ![08C9A637](https://github.com/user-attachments/assets/784774be-f010-4036-9615-45ea7ec6dfd9) Data


| Dataset | User | POI | Check-ins| Avg.Visit| Density|
| --------| --------| ------ |--------|----|------|
| **LA**  | 965     | 2,541  |37,181  | 39 | 1.5% |
| **NYC** | 1,083   | 9,989  |179,468 | 166| 1.7% |
| **SP**  | 3,722   | 12,829 |287,642 | 77 | 0.6% |
| **JK**  | 5,358   | 10,706 |300,324 | 56 | 0.5% |
| **IST** | 9,208   | 11,871 |529,067 | 57 | 0.5% |


* We have updated processed data in the './data/processed'. 
* For the raw data processing, we follow the Diff-POI data processing method.
* Due to the large file limit of GitHub, we cannot directly upload processed data of other dataset. We will update all of them in other link for more convenience after acceptance.

## ![08CA15E9](https://github.com/user-attachments/assets/772c218c-8b28-4b6f-a8de-fcee58c1bf25) Running

You can run this code on the uploaded LA dataset:

    python main.py --dataset la --batch 1024 --patience 10 --dropout --gpu 0 --keepprob 0.7
