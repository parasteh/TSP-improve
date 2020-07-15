# TSP-improve
This repo implements paper [Wu et. al., *Learning Improvement Heuristics for Solving Routing Problems*, arXiv, 2019](https://arxiv.org/abs/1912.05784v2), which solves TSP with the improvement-base Deep Reinforcement Learning method.

![tsp](./outputs/ep_gif_0.gif)

# Paper
For more details, please see the paper [Wu et. al., *Learning Improvement Heuristics for Solving Routing Problems*, arXiv, 2019](https://arxiv.org/abs/1912.05784v2).

```
@article{wu2019learning,
  title={Learning improvement heuristics for solving the travelling salesman problem},
  author={Wu, Yaoxin and Song, Wen and Cao, Zhiguang and Zhang, Jie and Lim, Andrew},
  journal={arXiv preprint arXiv:1912.05784},
  year={2019}
}
```

# Jupyter Notebook
We provide a Jupyter notebook to help you get started and understand our code. Please open the  [notebook here](file:/../../Solving%20TSP%20with%20Improvement-base%20DRL.ipynb) for more details.

# dependencies
* Python>=3.6
* PyTorch>=1.1
* numpy
* tqdm
* cv2
* tensorboard_logger
* imageio (optional, for plots)

## One more thing
For the exception below from package tensorboard_logger,
```python
AttributeError: module 'scipy.misc' has no attribute 'toimage'
```
Please refer to [issue #27](https://github.com/TeamHG-Memex/tensorboard_logger/issues/27) to fix it.

# Solving TSP
## Training
```python
CUDA_VISIBLE_DEVICES=0 python run.py --graph_size 20 --seed 1234 --n_epochs 100 --batch_size 512 --epoch_size 5120 --val_size 1000 --eval_batch_size 1000 --val_dataset './datasets/tsp_20_10000.pkl' --no_assert --run_name training
```

## Test only
```python
--eval_only --load_path '{add model to load here}'
```
Note: A pre-trained model can be found at './outputs/tsp_20/tsp_20200714T212735/epoch-99.pt'

# Acknowledgements
The code is  based on the repo [wouterkool/attention-learn-to-route](https://github.com/wouterkool/attention-learn-to-route) and the paper [Wu et. al., *Learning Improvement Heuristics for Solving Routing Problems*, arXiv, 2019](https://arxiv.org/abs/1912.05784v2).