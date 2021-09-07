# semantic_scenes_dataset
Official dataset for Semantic Implicit Neural Scene Representations With Semi-Supervised Training: https://arxiv.org/abs/2003.12673

Code coming soon!! For now please refer to https://github.com/vsitzmann/scene-representation-networks

Please run setup.sh in order to download the dataset 

The main directory contains all object directories (e.g., Chair)

Within each object directory is: 
    
    -the train/val/test split used in the paper.
    -Chair-level-1.txt: maps class labels (e.g., 0,1,2,..) to part names (e.g., chair back, chair arm, etc).
    -Chair.txt: shows hierarchy of parts (not used)


Each split contains a number of object instances (e.g., 800dd8ed32104151a37f3fc191551700)

Within in instance are the following elements:

    ├── intrinsics.txt                  # Camera intrinsic parameters used to render the images in rgb and seg
    ├── point_cloud                    # Contains point cloud data of the instance (not used)
    	├── sample-points-all-pts-nor-rgba-10000.txt			# point cloud stored as (x y z Nx Ny Nz R G B A)
	├── sample-points-label-10000.npy			# segmentation class labels for the above point clouds. 
    ├── pose                     # camera extrinsic parameters used to render each image in rgb and seg.
    	├── ...
    ├── result_after_merging.json                    # maps Partnet mesh indices to part names (not used)
    ├── result.json                   # maps Partnet mesh indices to part names for point clouds (not used)
    ├── rgb			# rgb images at each camera view, saved as .png files
    	├── ...
    └── seg			# segmentation maps at each camera view, saved as image-shaped numpy (.npy) arrays with per-pixel class labels
    	├── ...

	
    -intrinsics.txt:  camera intrinsic parameters used to render the images in rgb and seg
    -point_cloud:  contains point cloud data of the instance (not used)
	-sample-points-all-pts-nor-rgba-10000.txt: point cloud stored as (x y z Nx Ny Nz R G B A)
	-sample-points-label-10000.npy: segmentation class labels for the above point clouds. 

    -pose: camera extrinsic parameters used to render each image in rgb and seg.
    -result_after_merging.json: maps Partnet mesh indices to part names (not used)
    -result.json: maps Partnet mesh indices to part names for point clouds (not used)
    -rgb: rgb images at each camera view, saved as .png files
    -seg: segmentation maps at each camera view, saved as image-shaped numpy (.npy) arrays with per-pixel class labels

