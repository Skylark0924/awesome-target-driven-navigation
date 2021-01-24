#! https://zhuanlan.zhihu.com/p/338404758

![](https://pic4.zhimg.com/80/v2-e593771d9cc15546f31cfcfaa8459e2a.gif)

# Awesome Target-driven Navigation 资源汇总

|      Alias      | Target | Sensor  | SLAM |                          Framework                           |  Dataset  |    SR     |    SPL    | Note |
| :-------------------: | :-----: | :--: | :----------------------------------------------------------: | :-------: | :-------: | :-------: | :----: | :--: |
| [t-SNE](#t-SNE) |         Image         |   RGB   |  No  |                         ResNet + A3C                         |  AI2THOR  |     -     |     -     |      |
|  [SPTM](#SPTM)  |         Image         |   RGB   |  No  |                          DL + Graph                          | game Doom |     1     |     -     |      |
|   [NTS](#NTS)   |    panoramic image    | RGB/RGB | Yes  |    Graph Construction + Global Policy +<br />Local Policy    |  Gibson   | 0.55/0.63 | 0.38/0.43 |      |
|  [PTVN](#PTVN)  |    panoramic image    |  RGBD   |  No  |       autoencoder + policy  model +<br />goal checking       |   MP3D    |  0.8125   |  0.6614   |      |
|                 |                       |         |      |                                                              |           |           |           |      |
|       [CMP](#CMP)       |         Label         |   RGB/D   |      Yes |            Encoder-decoder+value iteration                                                 |    S3DIS + MP3D       |       0.638    |        0.228   |      |
| [Scene Priors](#Scene_Priors) |         Label         |   RGB   |  No  |                         GCN+LSTM+A3C                         |  AI2THOR  |   0.649   |   0.304   |      |
| [VR](#VR) |         Label         |   RGBD   |  No  |                         CNN+LSTM                         |  Active Vision Dataset (AVD)  |   0.54   |   -   |      |
|    [SAVN](#SAVN)    |         Label         |   RGB   |  No  |                ResNet18+GloVe+<br />LSTM+MAML                |  AI2THOR  |   0.287   |   0.139   |      |
|    [BRM](#BRM)    |         Label (Room)       |   RGBD   |  No  |                CNN+Graph+LSTM              |  House3D  |   0.231   |   0.045   |      |
|    [SF](#SF)    |         Label      |   RGBD   |  No  |                Situational Fusion              |  MP3D  |   0.44   |   -   |      |
|    [ORG](#ORG)    |         Label      |   RGB   |  No  |                GCN+LSTM+IL+TPN            |  AI2THOR  |   0.607   |   0.385  |      |
|     [MJOLNIR](#MJOLNIR)     |         Label         |   RGB   |  No  |                         GCN+LSTM+A3C                         |  AI2THOR  |   0.50   |   0.209    |      |
| [Attention 3D](#Attention_3D) |         Image         |   RGB   |  No  | LSTM A3C+KG+Attention |  AI2THOR  |   0.419   |   0.072   |      |
| [YouTube](#YouTube) |         Label         |   RGB   |  No  | Double DQN |  YouTube House Tours Dataset  |   0.79  |   0.53   |      |
| [SemExp](#SemExp) |         Label         |   RGBD   |  No  | Mask RCNN+Voxel Representation+RL |  MP3D  |   0.360   |  0.144    |

$^\dagger$ For methods designed for single room navigation, I use the result about a subset of targets whose optimal trajectory length is greater than 5 ($L\ge 5$).



## ImageGoal Navigation

1. **Target-driven Visual Navigation in Indoor Scenes using Deep Reinforcement Learning (<a id='t-SNE'>t-SNE</a>)**
   
   *Yuke Zhu, Roozbeh Mottaghi, Eric Kolve, Joseph J. Lim, Abhinav Gupta, Li Fei-Fei, Ali Farhadi* <br>
   ICRA, 2017. [[Paper\]](https://arxiv.org/abs/1609.05143) [[Website\]](https://prior.allenai.org/projects/target-driven-visual-navigation)

2. **Semi-Parametric Topological Memory for Navigation (<a id='SPTM'>SPTM</a>)**

   *Nikolay Savinov\*, Alexey Dosovitskiy\*, Vladlen Koltun* <br>
   ICLR, 2018. [[Paper\]](https://arxiv.org/pdf/1803.00653.pdf) [[Code\]](https://github.com/nsavinov/SPTM) [[Website\]](https://sites.google.com/view/SPTM)
   
3. **Neural Topological SLAM for Visual Navigation (<a id='NTS'>NTS</a>)**

   *Devendra Singh Chaplot, Ruslan Salakhutdinov, Abhinav Gupta, Saurabh Gupta* <br>
   CVPR, 2020. [[Paper\]](https://arxiv.org/pdf/2005.12256.pdf) [[Website\]](https://devendrachaplot.github.io/projects/Neural-Topological-SLAM)

4. **Learning Your Way Without Map or Compass: Panoramic Target  Driven Visual Navigation (<a id='PTVN'>PTVN</a>)**

   *David Watkins-Valls, Jingxi Xu, Nicholas Waytowich, Peter Allen*<br>
   \[[Paper](https://arxiv.org/pdf/1909.09295.pdf)\] 



## LabelGoal Navigation

1. **Cognitive Mapping and Planning for Visual Navigation (<a id='CMP'>CMP</a>)** 

   *Saurabh Gupta, Varun Tolani, James Davidson, Sergey Levine, Rahul Sukthankar, Jitendra Malik* <br>
   CVPR, 2017. [[Paper\]](https://arxiv.org/abs/1702.03920)

   <details>
   <summary>Summary</summary>

   Two key ideas:
   - a unified joint architecture for mapping and planning, such that the mapping is driven by the needs of the task;
   - a spatial memory with the ability to plan given an incomplete set of observations about the world. 
     

   CMP constructs a **top-down belief map** of the world and applies a **differentiable neural net planner** to produce the next action at each time step.

   **Network architecture**

   ![](https://pic4.zhimg.com/80/v2-43552d5cb2a856237915379ef05291cd.png)

   **Architecture of the mapper**

   ![](https://pic4.zhimg.com/80/v2-5d49149502c60e56e719faa306980afb.png)

   **Architecture of the hierarchical planner**

   ![](https://pic4.zhimg.com/80/v2-d07a07b61fe7c345d860729f385adb9f.png)
   </details>

2. **Visual Semantic Navigation using Scene Priors (<a id='Scene_Priors'>Scene Priors</a>)**

   *Wei Yang, Xiaolong Wang, Ali Farhadi, Abhinav Gupta, Roozbeh Mottaghi* <br>
   ICLR, 2019. [[Paper\]](https://arxiv.org/abs/1810.06543)

   <details>
   <summary>Summary</summary>

   They address navigation to **novel objects** or navigating in **unseen scenes** using **scene priors**, like human does.

   **Scene Priors**

   ![](https://pic4.zhimg.com/80/v2-85dd34e75e15aa6dd8340df9b394a40a.png)

   **Architecture**

   ![](https://pic4.zhimg.com/80/v2-f9aa32fe76ee17e120791f3dc8d95c3b.png)

   **GCN for relation graph embedding**

   ![](https://pic4.zhimg.com/80/v2-a2a7b13c4d6e6b4efe1ca2499989b00c.png)
   </details>

3. **Visual Representations for Semantic Target Driven Navigation (<a id='VR'>VR</a>)**

   *Arsalan Mousavian, Alexander Toshev, Marek Fiser, Jana Kosecka, Ayzaan Wahid, James Davidson* <br>
   ICRA, 2019. [[Paper\]](https://arxiv.org/pdf/1805.06066.pdf) [[Code\]](https://github.com/arsalan-mousavian/Navigation)

   <details>
   <summary>Summary</summary>
   
This paper focuses on finding a good **visual representation.**
   
![](https://pic4.zhimg.com/80/v2-673402901ca447c11dc3e97c6f8acd29.png)
   </details>
   
4. **Learning to Learn How to Learn: Self-Adaptive Visual Navigation using Meta-Learning (<a id='SAVN'>SAVN</a>)**

   *Mitchell Wortsman, Kiana Ehsani, Mohammad Rastegari, Ali Farhadi, Roozbeh Mottaghi* <br>
   CVPR, 2019. [[Paper\]](https://arxiv.org/abs/1812.00971) [[Code\]](https://github.com/allenai/savn) [[Website\]](https://prior.allenai.org/projects/savn)

   <details>
   <summary>Summary</summary>

   This paper uses **Meta-reinforcement learning** to construct an interaction loss for self-adaptive visual navigation. 

   ![](https://pic4.zhimg.com/80/v2-1d03aa2a1cb863d450ffd3f530957d2f.png)
   </details>

5. **Bayesian Relational Memory for Semantic Visual Navigation (<a id='BRM'>BRM</a>)**

   *Yi Wu, Yuxin Wu, Aviv Tamar, Stuart Russell, Georgia Gkioxari, Yuandong Tian* <br>
   ICCV, 2019. [[Paper\]](https://arxiv.org/abs/1909.04306) [[Code\]](https://github.com/jxwuyi/HouseNavAgent)

   <details>
   <summary>Summary</summary>

   Construct a probabilistic relation graph to learn the relationship or a topological memory of house layout.

   ![](https://pic4.zhimg.com/80/v2-096989e15a9789eed2c50e2a00aff508.png)
   </details>

6. **Situational Fusion of Visual Representation for Visual Navigation (<a id='SF'>SF</a>)**

   *William B. Shen, Danfei Xu, Yuke Zhu, Leonidas J. Guibas, Li Fei-Fei, Silvio Savarese* <br>
   ICCV, 2019. [[Paper\]](https://arxiv.org/abs/1908.09073)

   <details>
   <summary>Summary</summary>

   This paper aims at fusing multiple visual representations, such as Semantic Segment, Depth Perception, Object Class, Room Layout and Scene Class.

   They develop an action-level representation fusion scheme, which predicts an action candidate from each representation and adaptively consolidate these action candidates into the final action.

   ![](https://pic4.zhimg.com/80/v2-481cb84a66ab02e811cebd3b35456713.png)

   ![](https://pic4.zhimg.com/80/v2-1a442d44e9eb37dd851cd6fe4a1d1160.png)

   </details>

7. **Learning Object Relation Graph and Tentative Policy for Visual Navigation (<a id='ORG'>ORG</a>)**

   *Heming Du, Xin Yu, Liang Zheng* <br>
   ECCV, 2020. [[Paper\]](https://arxiv.org/abs/2007.11018)

   <details>
   <summary>Summary</summary>

   Aiming to learn informative visual representation and robust navigation policy, this paper proposes three complementary techniques, **object relation graph** (ORG), **trial-driven imitation learning** (IL), and a memory-augmented **tentative policy network** (TPN). 

   - ORG improves visual representation learning by integrating object relationships;
   - Both Trial-driven IL and TPN underlie robust navigation policy, in- structing the agent to escape from deadlock states, such as looping or being stuck;
   - IL is used in training, TPN for testing.
   
   ![](https://pic4.zhimg.com/80/v2-ed80c99ad90f5f2395b773045dbcc2fc.png)

   </details>

8. **Target driven visual navigation exploiting object relationships (<a id='MJOLNIR'>MJOLNIR</a>)** 

   *Yiding Qiu, Anwesan Pal, Henrik I. Christensen* <br>
   arxiv, 2020. [[Paper\]](http://arxiv.org/abs/2003.06749)

   <details>
   <summary>Summary</summary>

   They present Memory-utilized Joint hierarchical Object Learning for Navigation in Indoor Rooms (MJOLNIR)1, a target-driven visual navigation algorithm, which considers the inherent relationship between target objects, along with the more salient parent objects occurring in its surrounding.

   **MJOLNIR architecture**
   ![](https://pic4.zhimg.com/80/v2-33081b0bf51da76462fe1f49044d9929.png)

   **The novel CGN architecture**
   ![](https://pic4.zhimg.com/80/v2-d4e0edf649cd242c7ca7e5da06327563.png)
   </details>

9. **Improving Target-driven Visual Navigation with Attention on 3D Spatial Relationships (<a id='Attention_3D'>Attention 3D</a>)**

   *Yunlian Lv, Ning Xie, Yimin Shi, Zijiao Wang, and Heng Tao Shen* <br>
   arxiv, 2020. [[Paper\]](http://arxiv.org/abs/2005.02153)
   
   <details>
   <summary>Summary</summary>

   To address the **generalization and automatic obstacle avoidance** issues, we incorporate two designs into classic DRL framework: attention on 3D knowledge graph (KG) and target skill extension (TSE) module.

   - visual features and 3D spatial representations to learn navigation policy;
   - TSE module is used to generate sub-targets which allow agent to learn from failures.

   **Framework**

   ![](https://pic4.zhimg.com/80/v2-dce76c5ad0153abafd662d820c271eb6.png)

   **3D spatial representations**

   ![](https://pic4.zhimg.com/80/v2-5fd5e6a2620976fb678eeda7505ea9da.png)
   </details>

10. **Semantic Visual Navigation by Watching YouTube Videos (<a id='YouTube'>YouTube</a>)**
    
    *Matthew Chang, Arjun Gupta, Saurabh Gupta* <br>
    arXiv, 2020. [[Paper\]](https://arxiv.org/pdf/2006.10034.pdf) [[Website\]](https://matthewchang.github.io/value-learning-from-videos/)

      <details>
      <summary>Summary</summary>

      This paper **learns and leverages such semantic cues** for navigating to objects of interest in novel environments, **by simply watching YouTube videos**. They believe that these priors can improve efficiency for navigation in novel environments. 

      ![](https://pic4.zhimg.com/80/v2-a70ca29ea708b48b47735fcdd1b0c813.png)

      </details>

11. **Object Goal Navigation using Goal-Oriented Semantic Exploration (<a id='SemExp'>SemExp</a>)**

    *Devendra Singh Chaplot, Dhiraj Gandhi, Abhinav Gupta\*, Ruslan Salakhutdinov* <br>
    arXiv, 2020. [[Paper\]](https://arxiv.org/pdf/2007.00643.pdf) [[Website\]](https://devendrachaplot.github.io/projects/semantic-exploration)

    **Win CVPR2020 Habitat ObjectNav Challenge**
    

      <details>
      <summary>Summary</summary>

      They propose a modular system called, ‘**Goal- Oriented Semantic Exploration (SemExp)**’ which builds an episodic semantic map and uses it to explore the environment efficiently based on the goal object category.

      - It builds top-down metric maps, which adds extra channels to encode semantic categories explicitly;
      - Instead of using a coverage maximizing goal-agnostic exploration policy based only on obstacle maps, we train a goal-oriented semantic exploration policy which learns semantic priors for efficient navigation.

      **Framework**

      ![](https://pic4.zhimg.com/80/v2-cd820d5ebb9f890f6cfe1244a2609880.png)

      **Semantic Mapping**

      ![](https://pic4.zhimg.com/80/v2-c397c2ee6e0e18eb5b3f93d31a25d7f3.png)

      </details>

12. **ObjectNav Revisited: On Evaluation of Embodied Agents Navigating to Objects**

    *Dhruv Batra, Aaron Gokaslan, Aniruddha Kembhavi, Oleksandr Maksymets, Roozbeh Mottaghi, Manolis Savva, Alexander Toshev, Erik Wijmans* <br>
    arXiv, 2020. [[Paper\]](https://arxiv.org/abs/2006.13171)

      <details>
      <summary>Summary</summary>
    
      **This paper is not a research paper.** They summarize the ObjectNav task and introduce popular datasets (Matterport3D, AI2-THOR) and Challenges (Habitat 2020 Challenge Habitat, RoboTHOR 2020 Challenge RoboTHOR).

      </details>

---

知乎没法显示Summary部分的折叠和表格内部跳转，还不支持目录，格式真的太丑了，**再次请求支持完整版的 Markdown + HTML！！**
[@知乎小管家](https://www.zhihu.com/people/zhihuadmin)

欢迎移步 Github 观看正常版，**记得 Fork & Star 哦！**

[Awesome-Target-driven-Navigation/Skylark0924](https://github.com/Skylark0924/Awesome-Target-driven-Navigation)

