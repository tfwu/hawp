# Holistically-Attracted Wireframe Parsing (CVPR 2020)

This is the offical implementation for our [CVPR paper](https://arxiv.org/pdf/2003.01663).

## Highlights
- We propose **a fast and parsimonious parsing method HAWP** to accurately and robustly detect a vectorized wireframe in an input image with a single forward pass. 
- The proposed HAWP is **fully end-to-end**.
- The proposed HAWP **does not require squeeze module**.
- **State-of-the-art performance** on the Wireframe dataset and YorkUrban dataset.
- The proposed HAWP achievs **29.5 FPS** on a GPU (Tesla V100) for 1-batch inference.

<p align="center">
<img src="figures/teaser.png" height="400" >
<p>

## Quantitative Results

#### Wireframe Dataset

<table style="text-align:center" align="center">
<tr>
    <td rowspan="2" style="text-align:center"> Method </td> 
    <td colspan="7" style="text-align:center"> Wireframe Dataset </td>
    <td rowspan="2" style="text-align:center"> FPS </td>
</tr>
<tr >
    <td >sAP<sup>5</sup></td><td>sAP<sup>10</sup></td><td>sAP<sup>15</sup></td>
    <td>msAP</td><td>mAP<sup>J</sup></td><td>AP<sup>H</sup></td><td>F<sup>H</sup></td>    
</tr>
<tr>
  <td> LSD</td> <td>/</td> <td>/</td><td>/</td><td>/</td><td>/</td><td>55.2</td><td>62.5</td> <td>49.6</td>  
</tr>
<tr>
  <td> AFM</td> 
  <td>18.5</td> 
  <td>24.4</td>
  <td>27.5</td>
  <td>23.5</td>
  <td>23.3</td>
  <td>69.2</td>
  <td>77.2</td> <td>13.5</td>  
</tr>
<tr>
  <td> DWP</td> 
  <td>3.7</td> 
  <td>5.1</td>
  <td>5.9</td>
  <td>4.9</td>
  <td>40.9</td>
  <td>67.8</td>
  <td>72.2</td> <td>2.24</td>  
</tr>
<tr>
  <td rowspan="2"> L-CNN</td> 
  <td rowspan="2">58.9</td> 
  <td rowspan="2">62.9</td>
  <td rowspan="2">64.9</td>
  <td rowspan="2">62.2</td>
  <td rowspan="2">59.3</td>
  <td>80.3</td>
  <td>76.9</td> 
  <td rowspan="2">15.6</td>  
</tr>
<tr>
  <td>82.8<sup><span>&#8224;</span></sup>
</td><td>81.3<sup><span>&#8224;</span></sup></td>
</tr>
<tr>
  <td rowspan="2"> L-CNN (re-trained)</td> 
  <td rowspan="2">59.7</td> 
  <td rowspan="2">63.6</td>
  <td rowspan="2">65.3</td>
  <td rowspan="2">62.9</td>
  <td rowspan="2">60.2</td>
  <td>81.6</td>
  <td>77.9</td> 
  <td rowspan="2">15.6</td>  
</tr>
<tr>
  <td>83.7<sup><span>&#8224;</span></sup>
</td><td>81.7<sup><span>&#8224;</span></sup></td>
</tr>
<tr>
  <td rowspan="2"> <b>HAWP (Ours)</b></td> 
  <td rowspan="2"><b>62.5</b></td> 
  <td rowspan="2"><b>66.5</b></td>
  <td rowspan="2"><b>68.2</b></td>
  <td rowspan="2"><b>65.7</b></td>
  <td rowspan="2"><b>60.2</b></td>
  <td><b>84.5</b></td>
  <td><b>80.3</b></td> 
  <td rowspan="2">29.5</td>  
</tr>
<tr>
  <td><b>86.1</b><sup><span>&#8224;</span></sup>
</td><td><b>83.1</b><sup><span>&#8224;</span></sup></td>
</tr>  
</table>


<p align="left">
<img src="figures/sAP10-wireframe.png" height="260" >
<img src="figures/APH-wireframe.png" height="260" >
</p>




#### YorkUrban Dataset
<p align="center">
<table style="text-align:center">
<tr>
    <td rowspan="2" style="text-align:center"> Method </td> 
    <td colspan="7" style="text-align:center"> YorkUrban Dataset </td>
    <td rowspan="2" style="text-align:center"> FPS </td>
</tr>
<tr >
    <td >sAP<sup>5</sup></td><td>sAP<sup>10</sup></td><td>sAP<sup>15</sup></td>
    <td>msAP</td><td>mAP<sup>J</sup></td><td>AP<sup>H</sup></td><td>F<sup>H</sup></td>    
</tr>
<tr>
  <td> LSD</td> <td>/</td> <td>/</td><td>/</td><td>/</td><td>/</td><td>50.9</td><td>60.1</td> <td>49.6</td>  
</tr>
<tr>
  <td> AFM</td> 
  <td>7.3</td> 
  <td>9.4</td>
  <td>11.1</td>
  <td>9.3</td>
  <td>12.4</td>
  <td>48.2</td>
  <td>63.3</td> <td>13.5</td>  
</tr>
<tr>
  <td> DWP</td> 
  <td>1.5</td> 
  <td>2.1</td>
  <td>2.6</td>
  <td>2.1</td>
  <td>13.4</td>
  <td>51.0</td>
  <td>61.6</td> <td>2.24</td>  
</tr>
<tr>
  <td rowspan="2"> L-CNN</td> 
  <td rowspan="2">24.3</td> 
  <td rowspan="2">26.4</td>
  <td rowspan="2">27.5</td>
  <td rowspan="2">26.1</td>
  <td rowspan="2">30.4</td>
  <td>58.5</td>
  <td>61.8</td> 
  <td rowspan="2">15.6</td>  
</tr>
<tr>
  <td>59.6<sup><span>&#8224;</span></sup>
</td><td>65.3<sup><span>&#8224;</span></sup></td>
</tr>
<tr>
  <td rowspan="2"> L-CNN (re-trained)</td> 
  <td rowspan="2">25.0</td> 
  <td rowspan="2">27.1</td>
  <td rowspan="2">28.3</td>
  <td rowspan="2">26.8</td>
  <td rowspan="2">31.5</td>
  <td>58.3</td>
  <td>62.2</td> 
  <td rowspan="2">15.6</td>  
</tr>
<tr>
  <td>59.3<sup><span>&#8224;</span></sup>
</td><td>65.2<sup><span>&#8224;</span></sup></td>
</tr>
<tr>
  <td rowspan="2"> <b>HAWP (Ours)</b></td> 
  <td rowspan="2"><b>26.1</b></td> 
  <td rowspan="2"><b>28.5</b></td>
  <td rowspan="2"><b>29.7</b></td>
  <td rowspan="2"><b>28.1</b></td>
  <td rowspan="2"><b>31.6</b></td>
  <td><b>60.6</b></td>
  <td><b>64.8</b></td> 
  <td rowspan="2">29.5</td>  
</tr>
<tr>
  <td><b>61.2</b><sup><span>&#8224;</span></sup>
</td><td><b>66.3</b><sup><span>&#8224;</span></sup></td>
</tr>  
</table>
</p>


<p align="left">
<img src="figures/sAP10-york.png" height="260" >
<img src="figures/APH-york.png" height="260" >
<p>

## Installation & Pretrained Model

Will be finished in this week.

## Citations
If you find our work useful in your research, please consider citing:
```
@inproceedings{HAWP,
title = "Holistically-Attracted Wireframe Parsing",
author = "Nan Xue and Tianfu Wu and Song Bai and Fu-Dong Wang and Gui-Song Xia and Liangpei Zhang and Philip H.S. Torr
",
booktitle = "IEEE Conference on Computer Vision and Pattern Recognition (CVPR)",
year = {2020},
}
```

## Acknoledgement
We acknowledge the effort from the authors of the Wireframe dataset and the YorkUrban dataset. These datasets make accurate line segment detection and wireframe parsing possible.

