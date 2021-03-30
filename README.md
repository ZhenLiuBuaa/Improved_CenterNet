## Improved_CenterNet
This repository is based on [CenterNet](https://github.com/xingyizhou/CenterNet)
A simple improvement of CenterNet.

![Manhattan Error Distance of Samples](https://user-images.githubusercontent.com/45850504/112993240-8eff8180-919b-11eb-9f76-07d95dfa992f.png "Manhattan Error Distance of Samples")
As the figure shows, 47.8% wrong classified samples have 1 Manhattan Distance. So, we aims to add more modifications for those samples.
Add supervises for offset, size and gaussian distribution of samples with 1 Manhattan Error Distance.
The modifications consists of 3 parts: bbox size modification, bbox offset modification and gaussian distribution modification.
## BBox size modification:
![BBox size](https://user-images.githubusercontent.com/45850504/112994876-45b03180-919d-11eb-9744-f0bf07f875b8.png "BBox size")

As the fig shows, to the surrounding 8 points of the GT center point, we supervise the bbox size of these point. To get the best IOU score, we set new bbox size as n+2. And the min Iou is 

![image](https://user-images.githubusercontent.com/45850504/112995296-a8a1c880-919d-11eb-8e11-d7c8de60a4ad.png)
The yellow region is the GT bbox, and the black box is the modified bbox.

## Offset supervision
![Offset](https://user-images.githubusercontent.com/45850504/112995464-d6870d00-919d-11eb-97d2-90d1443c3e52.png "Offset")

As the figure shows, the black point is the GT center point, and the offset of surrerding points are shown as the black arrow. Theoretically, the modified offset can get the best Iou score.

## Heatmap gaussian distribution modification

![Heatmap](https://user-images.githubusercontent.com/45850504/112995895-472e2980-919e-11eb-93ed-a51ca4a55cb4.png "Heatmap")

As the figure shown, We consider the real Center point position rather than center point in hearmap to modify the gaussian dis.





