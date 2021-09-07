# semantic_scenes_dataset
Official dataset for Semantic Implicit Neural Scene Representations With Semi-Supervised Training: https://arxiv.org/abs/2003.12673

Code coming soon!! For now please refer to https://github.com/vsitzmann/scene-representation-networks

Please run `setup.sh` in order to download the dataset. It will create `semantic_srn_data/` and download the `Chair/` and `Table/` directories from box.com into it.

The main directory contains all object directories (e.g., Chair) 
	
	.
	├── semantic_srn_data
		├── Chair
			├── Chair.train
			├── Chair.val
			├── Chair.test
			├── Chair.txt			# Shows hierarchy of parts (not used)
			└── Chair-level-1.txt		# Maps class labels (e.g., 0,1,2,..) to part names (e.g., chair back, chair arm, etc).
		└── Table
			├── ...				# Same as Chair




Each split (e.g., Chair.val) contains a number of object instances (e.g., 800dd8ed32104151a37f3fc191551700)
	
	├── ...
	├── Chair.val
		├── ...
		├── 800dd8ed32104151a37f3fc191551700 		# Single object instance (e.g., lawn chair)
		└── ...
	└── ...

Within each instance are the following elements:

	.
	├── 800dd8ed32104151a37f3fc191551700 		# Single object instance (e.g., lawn chair)
		├── intrinsics.txt                 # Camera intrinsic parameters used to render the images in rgb and seg
		├── point_cloud                    # Contains point cloud data of the instance (not used)
			├── sample-points-all-pts-nor-rgba-10000.txt		# point cloud stored as (x y z Nx Ny Nz R G B A)
			├── sample-points-label-10000.npy			# segmentation class labels for the above point clouds. 
		├── result_after_merging.json      # maps Partnet mesh indices to part names (not used)
		├── result.json                    # maps Partnet mesh indices to part names for point clouds (not used)
		├── pose                           # camera extrinsic parameters used to render each image in rgb and seg.
			├── ...
		├── rgb			      	   # rgb images at each camera view, saved as .png files
			├── ...
		└── seg			           # segmentation maps at each camera view, saved as image-shaped numpy (.npy) arrays with per-pixel class labels
			├── ...
	
