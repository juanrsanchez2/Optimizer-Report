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

### Adam Optimizer

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
![Adam Easy Starting Point](adam-easy.png)

**Long Run - N iter: 10157**
![Adam Easy Starting Point](adam-easy-long.png)

### Medium Starting Point
**Short Run - N iter: 1285**
<p>
  <img src="adam-med.png" width="49%">
  <img src="adam-med-p2.png" width="49%">  
</p>

**Long Run - N iter: 10157**
<p>
  <img src="adam-med-long.png" width="49%">
  <img src="adam-med-long-p2.png" width="49%">  
</p>
<p>
  <img src="adam-med-long-p3.png" width="49%">
  <img src="adam-med-long-p4.png" width="49%">  
</p>

### Hard Starting Point
**Short Run - N iter: 1285**
<p>
  <img src="adam-hard.png" width="49%">
  <img src="adam-hard-p2.png" width="49%">  
</p>

**Long Run - N iter: 10157**
<p>
  <img src="adam-hard-long.png" width="49%">
  <img src="adam-hard-long-p2.png" width="49%">  
</p>
<p>
  <img src="adam-hard-long-p3.png" width="49%">
  <img src="adam-hard-long-p4.png" width="49%">  
</p>

### Adam Analysis

For the easy starting point (1.0, -.1,0), Adam optimizer went directly towards the global minimum just like the previous two optimizers SGD/RMSprop. For the long run, upon inspection of the extremely zoomed image, you can see that Adam continued towards the global minimum, there was still some micro-optimization saved points.

For the medium starting point (4.0, 1.0), Adam optimizer moved towards the local minimum it was closest to on both short and long runs. Upon closer inspection of the long run, on multiple extremely zoomed images, the Adam optimizer showed optimization movements around the local minimum. It eventually created a square like figure that circled the local minimum. 

For the hard starting point (-6.0, -3.0), Adam optimizer converged towards its nearest local minimum just like the two previous optimizers. Just likes the Easy/Medium starting points, the long run shows micro-optimization movements as it heads toward the local minimum. 

Overall, Adam optimizer was stable and did converge to a minimum from all three starting points. However, similarly like SGD and RMSprop, it did not make an attempt to exit its local minimum and head towards the global minimum. From this experiment, the starting point seems to affect where it converges. Just like SGD/RMSprop, it converges at its nearest minimum instead of heading towards the global minimum.

## 4. Comparison and Analysis

### 1. which optimizer converged fastest?
Adam seems to be the fastest at converging at the minimum based on the pathing of the three optimizers, however, it also does show a lot of micro-optimization adjustments as it went towards the final destination.

### 2. Which optimizer was the most stable?
SGD was the most stable optimizer; it had visible less oscillation even at an extremely zoomed image compared to Adam and RMSprop.

### 3. Which optimizer struggled the most?
RMSprop seemed to struggle the most. While it did oscillate like Adam, as seen in the medium/hard runs, it had quite more oscillation approaching its final destination compared to Adam.

### 4. Which optimizer handled the hard starting point best?
RMSprop handled the hard starting point best. From the path it took, RMSprop got closer to the local minimum faster even though it had more oscillation once it was there.

### 5. Which optimizer would you choose for a real machine learning problem and why?
I would choose RMSprop for a real machine learning problem. From my experiments, RMSprop was able to move towards the minimum faster, even though it had more oscillation around the final destination. I would accept that oscillation as a negligible loss since it was micro-movements around the final destination and it was close to the result I was looking for.

## 5. Conclusion
The experiment revealed how different each optimizer can be even when using the same parameters. Starting Point was a major effect on each of the optimizers and where they would converge since medium and hard starting points led all three optimizers to head towards the nearest local minimum instead of the global minimum. SGD showed to be the most stable, while RMSprop reached the area near the minimum the fastest even though it had more oscillation once it was there, and Adam also reached the minimum quickly with micro-optimization movements near the minimum. There are pros and cons for each optimizter. Overall, depending on the needs of your real machine learning problem and what you need, such as getting there faster but less accurate, getting there fast but having more oscillation near the minimum, or a good mixture between the two and arriving relatively quickly with some micro-optimization movements around the final destination. 




