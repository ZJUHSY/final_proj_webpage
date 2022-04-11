# Pathtracer Speed-up Optimization 

## Team Member

Songye Han: EECS Master of Engineering student (CS284A) \
Tianyi Huang: EECS Master of Engineering student (CS284A) \
Mingyue Fan: EECS Master of Engineering student (CS284A) \
Tian Liu: CS Bachelor of Art student (CS184) 

## Summary

In our project, we are going to optimize and speed up the BVH process of ray tracing from our course project 3-1. Also, we will seek other alternative acceleration structures such as K-D tree and bidirectional path tracing. 

## Problem Description

In the previous path tracer project 3-1, the optimization method we used is based on a recursive call of BVH construction and partition. While this method did speed up the construction and rendering processes, it still takes several minutes to render mesh-complex and high resolution images. Although the previous framework was already constructed with a solid BVH acceleration structure, there are many aspects which can be improved in the old framework including optimizing memory space and time complexity of the current BVH algorithm. Also, we can create more fancy visual effects such as motion blurring and denoising. 

Besides, we can use other alternative algorithms to speed up the ray tracer. For example, we can implement acceleration structures such as k-d tree and octree, use Bidirectional path tracing (BDPT) , or leverage GPU to substantially speed up the construction and rendering time for much more complex scenes.  
## Goals and Deliverables

### Image Type
The original image type we use for rendering is dae file type, which is a 3D interactive file format that can be used to exchange digital data between multiple graphics programs. And the image type we plan to render is the same as that in assignment 3-1 and 3-2, which can be divided into GUI interface in debugging mode and PNG format image for rendering results.

### Metrics & Measurements
For the optimization of our BVH and other acceleration structures, we evaluate the performance by the graphs showing speedup compared to our baseline. For other optimization aspects such as motion blurring, we check the performance of our method by the rendered output images. 

### Questions

For the first part of the project, we plan to speed up the construction and rendering time by completing the following steps:

#### Expected Deliverables
- Speed Up of BVH: (1) Optimizing BVH splitting method by using surface area heuristic instead of current naive heuristic; (2) Optimizing the BVH process’s speed by replacing the recursive calls with a stack and while loop. We compare the performance improvement against the original construct by performing rendering on different dae files.
- BVH Memory Optimization: Optimizing the memory usage of the BVH construct by changing the pointers and compressing the tree. We compare the memory usage against the original construct by performing the same rendering as task 1.
- Implementing other acceleration structures such as k-d tree and octree to speed up the rendering process

We expect to achieve a 50% speed-up when finishing the expected deliverables. 

#### Extra Deliverables
- Implement Bidirectional path tracing (BDPT) algorithm to further optimize the overall efficiency of rendering. BDPT introduces a bidirectional sampling framework which samples start points from both sides, the light source and the eye. Also, it uses the  importance sampling to integrate over different paths, which is similar to one-direciton path tracing. 
- Realizing parallel physical acceleration through GPU, we will use CUDA and other frameworks to deploy graphics algorithms to GPU level, and achieve parallel rendering of image through distributed computing.

We expect to achieve a 200% speed-up when finishing the extra deliverables. 

## Schedule

Week 1 (4.10-4.16): Complete the first two steps of our expected deliverables which mainly focuses on optimizing the original naive BVH algorithm to speed up rendering time and save its memory; write the report webpage. \
Week 2 (4.17-4.23): Complete the third part of our expected deliverables which mainly focus on implementing K-D Tree and octree to further speed up rendering process; collect related reference materials of BDPT and GPU graphics acceleration; write the report webpage and prepare the milestone video. \
Week 3 (4.24-4.30): Get familiar with the mechanisms of BDPT and CUDA and try to implement one of the two; prepare for the final presentations, including making slides and assigning works of presentation. \
Week 4 (5.1-5.7): Gather and summarize all completed optimization results. Create visuals and slides for presentation

## Resources

K-d Tree: [Resource](https://www.cs.cmu.edu/~ckingsf/bioinfo-lectures/kdtrees.pdf)
Octree: [Resource](http://www.open3d.org/docs/release/tutorial/geometry/octree.html)
Bidirectional path tracing: [Resource](https://www.pbr-book.org/3ed-2018/Light_Transport_III_Bidirectional_Methods/Bidirectional_Path_Tracing)
CUDA: [Resource](https://nyu-cds.github.io/python-gpu/02-cuda/)
