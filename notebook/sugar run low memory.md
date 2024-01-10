
https://github.com/Anttwo/SuGaR/issues/40#issuecomment-1867142488

1. modified this [code](https://github.com/Anttwo/SuGaR/blob/72b9baa942593a8d3d7ef205288788821cedb1e8/sugar_scene/cameras.py#L100C65-L100C65), `image_height=image_height, image_width=image_width, data_device='cpu')`
2. move the image to cuda during training process, modified this [code](https://github.com/Anttwo/SuGaR/blob/72b9baa942593a8d3d7ef205288788821cedb1e8/sugar_trainers/coarse_sdf.py#L521C81-L521C81) `gt_image = nerfmodel.get_gt_image(camera_indices=camera_indices).cuda()`
3. same action in `coarse_density.py` and `refined.py`



https://github.com/Anttwo/SuGaR/issues/40#issuecomment-1865933630

1. reduce image size
2. reduce gauss-points (important, BUT maybe your images are very complex.)




https://github.com/Anttwo/SuGaR/issues/40#issuecomment-1866622069
	os.environ["PYTORCH_NO_CUDA_MEMORY_CACHING"]= "1"
	torch.cuda.empty_cache()







https://github.com/Anttwo/SuGaR/issues/45#issuecomment-1870693547
	
	You can try to reduce the number of vertices in the coarse mesh. Using `--low_poly` will drop the number to 200k, but you can adjust the number by yourself (and use, for example, 800k vertices) with the argument `--n_vertices_in_mesh`. Please refer to the README.md file for more details about the arguments.



