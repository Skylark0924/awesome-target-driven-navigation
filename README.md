# Awesome Target-driven Navigation




|      Alias      | Target (label, image) | Sensor  | SLAM |                          Framework                           |  Dataset  |    SR     |    SPL    | Note |
| :-------------: | :-------------------: | :-----: | :--: | :----------------------------------------------------------: | :-------: | :-------: | :-------: | ---- |
| [t-SNE](#t-SNE) |         Image         |   RGB   |  No  |                         ResNet + A3C                         |  AI2THOR  |     -     |     -     |      |
|  [SPTM](#SPTM)  |         Image         |   RGB   |  No  |                          DL + Graph                          | game Doom |     1     |     -     |      |
|   [NTS](#NTS)   |    panoramic image    | RGB/RGB | Yes  |    Graph Construction + Global Policy +<br />Local Policy    |  Gibson   | 0.55/0.63 | 0.38/0.43 |      |
|  [PTVN](#PTVN)  |    panoramic image    |  RGBD   |  No  |       autoencoder + policy  model +<br />goal checking       |   MP3D    |  0.8125   |  0.6614   |      |
|                 |                       |         |      |                                                              |           |           |           |      |
|       CMP       |         Label         |   RGB   |      |                                                              |           |           |           |      |
|  Scene priors   |         Label         |   RGB   |  No  |                         GCN+LSTM+A3C                         |  AI2THOR  |   0.354   |   0.109   |      |
|      SAVN       |         Label         |   RGB   |  No  |                ResNet18+GloVe+<br />LSTM+MAML                |  AI2THOR  |   0.357   |   0.093   |      |
|     MJOLNIR     |         Label         |   RGB   |  No  |                         GCN+LSTM+A3C                         |  AI2THOR  |   0.653   |   0.21    |      |
|                 |         Image         |   RGB   |  No  | attention on 3D knowledge graph  (KG) and target skill extension (TSE) module. |  AI2THOR  |   0.419   |   0.072   |      |
|                 |                       |         |      |                                                              |  AI2THOR  |   0.607   |   0.386   |      |
|                 |                       |         |      |                                                              |           |           |           |      |
|                 |                       |         |      |                                                              |           |           |           |      |
|                 |                       |         |      |                                                              |           |           |           |      |
|                 |                       |         |      |                                                              |           |           |           |      |
|                 |                       |         |      |                                                              |           |           |           |      |



## ImageGoal Navigation

1. **Target-driven Visual Navigation in Indoor Scenes using Deep Reinforcement Learning (<a id='t-SNE'>t-SNE</a>)**\\
   *Yuke Zhu, Roozbeh Mottaghi, Eric Kolve, Joseph J. Lim, Abhinav Gupta, Li Fei-Fei, Ali Farhadi*\\
   ICRA, 2017. [[Paper\]](https://arxiv.org/abs/1609.05143) [[Website\]](https://prior.allenai.org/projects/target-driven-visual-navigation)

2. **Semi-Parametric Topological Memory for Navigation (<a id='SPTM'>SPTM</a>)**\\
   *Nikolay Savinov\*, Alexey Dosovitskiy\*, Vladlen Koltun*\\
   ICLR, 2018. [[Paper\]](https://arxiv.org/pdf/1803.00653.pdf) [[Code\]](https://github.com/nsavinov/SPTM) [[Website\]](https://sites.google.com/view/SPTM)
   
3. **Neural Topological SLAM for Visual Navigation (<a id='NTS'>NTS</a>)**
   *Devendra Singh Chaplot, Ruslan Salakhutdinov, Abhinav Gupta, Saurabh Gupta*
   CVPR, 2020. [[Paper\]](https://arxiv.org/pdf/2005.12256.pdf) [[Website\]](https://devendrachaplot.github.io/projects/Neural-Topological-SLAM)

4. **Learning Your Way Without Map or Compass: Panoramic Target  Driven Visual Navigation (<a id='PTVN'>PTVN</a>)**
   *David Watkins-Valls, Jingxi Xu, Nicholas Waytowich, Peter Allen*
   \[[Paper](https://arxiv.org/pdf/1909.09295.pdf)\] 



## LabelGoal Navigation

1. **Cognitive Mapping and Planning for Visual Navigation (CMP)** 

   *Saurabh Gupta, Varun Tolani, James Davidson, Sergey Levine, Rahul Sukthankar, Jitendra Malik* 
   CVPR, 2017. [[Paper\]](https://arxiv.org/abs/1702.03920)

2. **Visual Semantic Navigation using Scene Priors (Scene Priors)**

   *Wei Yang, Xiaolong Wang, Ali Farhadi, Abhinav Gupta, Roozbeh Mottaghi* 
   ICLR, 2019. [[Paper\]](https://arxiv.org/abs/1810.06543)

3. **Visual Representations for Semantic Target Driven Navigation**

   *Arsalan Mousavian, Alexander Toshev, Marek Fiser, Jana Kosecka, Ayzaan Wahid, James Davidson* 
   ICRA, 2019. [[Paper\]](https://arxiv.org/pdf/1805.06066.pdf) [[Code\]](https://github.com/arsalan-mousavian/Navigation)

4. **Learning to Learn How to Learn: Self-Adaptive Visual Navigation using Meta-Learning (SAVN)**

   *Mitchell Wortsman, Kiana Ehsani, Mohammad Rastegari, Ali Farhadi, Roozbeh Mottaghi* 
   CVPR, 2019. [[Paper\]](https://arxiv.org/abs/1812.00971) [[Code\]](https://github.com/allenai/savn) [[Website\]](https://prior.allenai.org/projects/savn)

5. **Bayesian Relational Memory for Semantic Visual Navigation (BRM)**

   *Yi Wu, Yuxin Wu, Aviv Tamar, Stuart Russell, Georgia Gkioxari, Yuandong Tian* 
   ICCV, 2019. [[Paper\]](https://arxiv.org/abs/1909.04306) [[Code\]](https://github.com/jxwuyi/HouseNavAgent)

6. **Situational Fusion of Visual Representation for Visual Navigation **

   *William B. Shen, Danfei Xu, Yuke Zhu, Leonidas J. Guibas, Li Fei-Fei, Silvio Savarese* 
   ICCV, 2019. [[Paper\]](https://arxiv.org/abs/1908.09073)

7. **Learning Object Relation Graph and Tentative Policy for Visual Navigation**

   *Heming Du, Xin Yu, Liang Zheng* 
   ECCV, 2020. [[Paper\]](https://arxiv.org/abs/2007.11018)

8. **Target driven visual navigation exploiting object relationships (MJOLNIR)** 

9. **Improving Target-driven Visual Navigation with Attention on 3D Spatial Relationships (Attention 3D)**

10. **Semantic Visual Navigation by Watching YouTube Videos **

    *Matthew Chang, Arjun Gupta, Saurabh Gupta* 
    arXiv, 2020. [[Paper\]](https://arxiv.org/pdf/2006.10034.pdf) [[Website\]](https://matthewchang.github.io/value-learning-from-videos/)

11. **Object Goal Navigation using Goal-Oriented Semantic Exploration**

    *Devendra Singh Chaplot, Dhiraj Gandhi, Abhinav Gupta\*, Ruslan Salakhutdinov*
    arXiv, 2020. [[Paper\]](https://arxiv.org/pdf/2007.00643.pdf) [[Website\]](https://devendrachaplot.github.io/projects/semantic-exploration)

12. **ObjectNav Revisited: On Evaluation of Embodied Agents Navigating to Objects**

    *Dhruv Batra, Aaron Gokaslan, Aniruddha Kembhavi, Oleksandr Maksymets, Roozbeh Mottaghi, Manolis Savva, Alexander Toshev, Erik Wijmans* 
    arXiv, 2020. [[Paper\]](https://arxiv.org/abs/2006.13171)

