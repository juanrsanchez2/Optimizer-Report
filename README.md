# Optimizer-Report

## 1. Introduction
Optimizers are formulas used in machine learning that reduce loss/errors and make their predictions more accurate. Optimizers are not all equal, depending on your choice will affect how well the model's efficiency is and how fast the model converges. In this experiment, I compared three different optimizers **<ins>SGD, RMSprop, and Adam</ins>**. I tested each of these optimizers at different starting points and observed their optimization paths and where they converged. 

## 2. Experiment Setup
Each of the optimizers were tested using the same three different starting points, which each of the three starting points ranging to what I consider **Easy, Medium, Hard** difficulty. The same settings were used across the board for each difficulty to ensure that each optimizer had the same conditions when the experiment ran.

| Experiment | Starting Point | Why I Chose It | N iter (Short) | N iter (Long) |Log iter |
|---|---|---|---|---|---|
| Easy | (1.0, -1,0) | Near the global minimum | 1285 | 10157 | 100 |
| Medium | (4.0, 1.0) | On the outer region near a local minimum | 1285 | 10157 | 100 |
| Hard | (-6.0, -3.0) | Near a local minimum farther from the global minimum | 1285 | 10157 | 100 |

## 3. Optimizer Results
### SGD Optimizer

**Starting Points Tested:**
- Easy: (1.0, -1.0)
- Medium: (4.0, 1.0)
- Hard: (-6, -3)

**Settings:**
- N iter (Short): 1285
- N iter (Long): 10157
- Log iter: 100
- Learning Rate: 0.01

### Easy Starting Point
**Short Run - N iter: 1285**
![SGD Easy Starting Point](sgd-easy.png)

**Long Run - N iter: 10157**
![SGD Easy Starting Point](sgd-easy-long.png)

### Medium Starting Point
**Short Run - N iter: 1285**
![SGD Medium Starting Point](sgd-med.png)

**Long Run - N iter: 10157**
<p>
  <img src="sgd-med-long.png" width="32%">
  <img src="sgd-med-long-p2.png" width="32%">
  <img src="sgd-med-long-p3.png" width="32%">
</p>

### Hard Starting Point
**Short Run - N iter: 1285**
![SGD Hard Starting Point](sgd-hard.png)

**Long Run - N iter: 10157**
<p>
  <img src="sgd-hard-long.png" width="32%">
  <img src="sgd-hard-long-p2.png" width="32%">
  <img src="sgd-hard-long-p3.png" width="32%">
</p>

### SGD Analysis
For the easy starting point (1.0, -1,0), SGD optimizer moved toward the global minimum. The path was straight foward with what looks like almost no adjustments. The longer run yielded the same results. This likely due to being position relatively close to the global minimum.

For the medium starting point (4.0, 1.0), SGD optimizer moved toward a local minimum and continued to converge at that local minimum in both short and long runs. Upon closer inspection of the long run, you can notice that there were micro adjustments made as it converged at the local minimum.

For the hard starting point (-6.0, -3.0), SGD optimizer also moved toward a local minimum and continued to converge at that local minimum in both short and long runs. Just like the medium starting point, when you take a closer look at the long runs path, you can see that it continues to make micro adjustments as it gets closer to the local minimumm.

The SGD optimizer seems to to be stable, as their paths were direct and micro adjustments were made as they approached a minimum. However, it should be noted that neither runs in the medium or hard tests made any attempt at converging to the global minimum. From these tests it seems that the starting points directly affected where SGD optimizer would converge, it seems to converge at its nearest minimum rather than just trying to get to the global minimum.

### RMSprop Optimizer

**Starting Points Tested:**
- Easy: (1.0, -1.0)
- Medium: (4.0, 1.0)
- Hard: (-6, -3)

**Settings:**
- N iter (Short): 1285
- N iter (Long): 10157
- Log iter: 100
- Learning Rate: 0.01

### Easy Starting Point
**Short Run - N iter: 1285**
![RMSprop Easy Starting Point](rms-easy.png)

**Long Run - N iter: 10157**
![RMSprop Easy Starting Point](rms-easy-long.png)  

### Medium Starting Point
**Short Run - N iter: 1285**
<p>
  <img src="rms-med.png" width="49%">
  <img src="rms-med-p2.png" width="49%">
</p>

**Long Run - N iter: 10157**
<p>
  <img src="rms-med-long.png" width="49%">
  <img src="rms-med-long-p2.png" width="49%">
</p>
<p>
  <img src="rms-med-long-p3.png" width="49%">
  <img src="rms-med-long-p4.png" width="49%">
</p>

### Hard Starting Point
**Short Run - N iter: 1285**
<p>
  <img src="rms-hard.png" width="49%">
  <img src="rms-hard-p2.png" width="49%">
</p>

**Long Run - N iter: 10157**
<p>
  <img src="rms-hard-long.png" width="49%">
  <img src="rms-hard-long-p2.png" width="49%">
</p>
<p>
  <img src="rms-hard-long-p3.png" width="49%">
  <img src="rms-hard-long-p4.png" width="49%">
</p>

### RMSprop Analysis
For the easy starting point (1.0, -1.0), RMS optimizer in both short and long runs moved directly towards the center of the global minimum. The longer run however continued optimizing as it approached the global minimum.

For the medium starting point (4.0, 1,0), RMS optimizer moved towards its nearest local minimum. In both short and long runs, you noticed that they both converged at the local minimum. However, at a much close inspection of the long run, you notice it oscillates near the minimum, denoted by the two parallel lines on the extreme zoom on that last image.

For the hard starting point (-6, -3.0, RMS optimizer also moved towards it nearest local minimum. While both short and long runs both converge at their local minimum at first glance. Upon extreme zoom inspection of the long run, there was oscillation around the local minimum, denoted by the irregular pathing near the local minimum.

The RMSprop optimizer was overall stable. It did show more movement around the minimum when viewed at an extreme zooming scale. This is especially true for the long runs, while at a microscopic level, there was noticeable movement around the minimum. Despite the increasing movement around the local minimum, there was no attempt to leave it and converge at the global minimum. The starting point seems to also affect where its convergence point will be. From these tests, it seems to converge at its nearest minimum instead of converging at the global minimum.
