# NYCU-perception-and-decision-making-in-intelligent-systems-hw2

In this homework, we

- Train a semantic segmentation model to predict objects in the
    
    There are two dataset we would like to train.
    
    - Dataset1: Collect data from apartment_1, apartment_2, frl_apartment_0,
    frl_apartment_1, room_0, room_1 , room_2, hotel_0, office_0, office_1.
    - Dataset2: Collect data from apartment_0 (the same as testing scenario).
    
    You can download data using link below.
    
    [https://docs.google.com/document/d/1PCaJ2L7kWUCN7w7erHnxOBDoCcsuIic5/edit](https://docs.google.com/document/d/1PCaJ2L7kWUCN7w7erHnxOBDoCcsuIic5/edit)
    
    model other: trained by other scenes.
    
    model apartment_0: trained by apartment_0. 
    
    We can observe the **domain shift** in this task.
    
- Reconstruat the 3D semantic map environment of Replica
- Implement our own voxel down function

---

## Execution program

You have the option to choose from two models, two floors, and two ICP (Iterative Closest Point) algorithms.

-f 1

-f 2

-d dataset1

-d dataset2

-v open3d

-v myicp

e.g. Below, it means using the Open3D algorithm for floor 1 and pictures trained by dataset2.

```
python 3d_semantic_map.py -f 1 -d dataset2 -v open3d
```

you have to put the data like below

```
data_collection_dataset1
	-first_floor
		-depth
			-1.png
			...
		-gt
			-1.png
			...
		-sem
			-1.png
			...
	-second_floor
		-depth
			-1.png
			...
		-gt
			-1.png
			...
		-sem
			-1.png
			...
data_collection_dataset2
	-first_floor
		-depth
			-1.png
			...
		-gt
			-1.png
			...
		-sem
			-1.png
			...
	-second_floor
		-depth
			-1.png
			...
		-gt
			-1.png
			...
		-sem
			-1.png
			...
```

---

## Results

Task1:

- Pictures trained by Dataset1/ floor1
    
    
                      rgb 			                 ground truth                                 prediction	
    
    ![1.png](https://github.com/randy2332/NYCU-perception-and-decision-making-in-intelligent-systems-hw2/blob/main/pictures/1.png)
    
- Pictures trained by Dataset1/ floor2
    
                      rgb 			                 ground truth                                 prediction	
    
    ![2.png](https://github.com/randy2332/NYCU-perception-and-decision-making-in-intelligent-systems-hw2/blob/main/pictures/2.png)
    
- Pictures trained by Dataset2/ floor1
    
                      rgb 			                 ground truth                                 prediction	
    
    ![3.png](https://github.com/randy2332/NYCU-perception-and-decision-making-in-intelligent-systems-hw2/blob/main/pictures/3.png)
    
- Pictures trained by Dataset2/ floor2
    
                      rgb 			                 ground truth                                 prediction	
    
    ![4.png](https://github.com/randy2332/NYCU-perception-and-decision-making-in-intelligent-systems-hw2/blob/main/pictures/4.png)
    
                                                Iou and accuracy
    
    |  | floor1 | floor2 |
    | --- | --- | --- |
    | Dataset1 Mean Iou | 0.2159 | 0.3699 |
    | Dataset1 Accuracy | 62.16% | 63.94% |
    | Dataset2 Mean Iou | 0.6035 | 0.65 |
    | Dataset2 Accuracy | 90.75% | 92.95% |
    
    Referece:
    
    [https://github.com/CSAILVision/semantic-segmentation-pytorch](https://github.com/CSAILVision/semantic-segmentation-pytorch)
    
    [https://github.com/open-mmlab/mmsegmentation](https://github.com/open-mmlab/mmsegmentation)
    
    [https://hackmd.io/wNGlmMq2RC-lY3l8JhO4SA?view](https://hackmd.io/wNGlmMq2RC-lY3l8JhO4SA?view)
    
    [https://stackoverflow.com/questions/62461379/multiclass-semantic-segmentation-model-evaluation](https://stackoverflow.com/questions/62461379/multiclass-semantic-segmentation-model-evaluation)
    
    Task2:
    
- floor1

  -Semantic map (ground truth)

![dataset1floor1gt.png](https://github.com/randy2332/NYCU-perception-and-decision-making-in-intelligent-systems-hw2/blob/main/pictures/floor1gt.png)

  -Semantic map (trained on apartment_0)

![dataset2floor1result.png](https://github.com/randy2332/NYCU-perception-and-decision-making-in-intelligent-systems-hw2/blob/main/pictures/dataset2floor1result.png)

  -Semantic map (trained on other scenes)

![dataset1floor1result.png](https://github.com/randy2332/NYCU-perception-and-decision-making-in-intelligent-systems-hw2/blob/main/pictures/dataset1floor1result.png)

- floor2

  -Semantic map (ground truth)

![floor2gt.png](https://github.com/randy2332/NYCU-perception-and-decision-making-in-intelligent-systems-hw2/blob/main/pictures/floor2gt.png)

  -Semantic map (trained on apartment_0)

![dataset2floor2result.png](https://github.com/randy2332/NYCU-perception-and-decision-making-in-intelligent-systems-hw2/blob/main/pictures/dataset2floor2result.png)

  -Semantic map (trained on other scenes)

![dataset1floor2result.png](https://github.com/randy2332/NYCU-perception-and-decision-making-in-intelligent-systems-hw2/blob/main/pictures/dataset1floor2result.png)
