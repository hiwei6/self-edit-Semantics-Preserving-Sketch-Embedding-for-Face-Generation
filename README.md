# Semantics-Preserving Sketch Embedding for Face Generation
![Teaser](figure/teaser_1.jpg)
### [Paper](https://arxiv.org/abs/2211.13015) 
<!-- <br> -->
[Binxin Yang](https://orcid.org/0000-0003-4110-1986), [Xuejin Chen](http://staff.ustc.edu.cn/~xjchen99/), Chaoqun Wang, Chi Zhang, Zihan Chen, [Xiaoyan Sun](http://staff.ustc.edu.cn/~xysun720/).
<!-- <br> -->

## To train the stylegan2, train the stylegan2 in the enviroment and package
We implement fine-tuning on the pre-trained generator based on the paper above 
https://github.com/rosinality/stylegan2-pytorch


## Requirements
A suitable [conda](https://conda.io/) environment named `psp_env` can be created
and activated with:

```
conda env create -f psp_env.yaml
conda activate psp_env
```

## Pretrained Model
We provide the checkpoint ([Google Drive](https://drive.google.com/file/d/1jyoEqZXNfsz-MOlRSimjwG3q8GdeA4AZ/view?usp=share_link)) that is trained on [CelebAMask-HQ](https://github.com/switchablenorms/CelebAMask-HQ). By default, we assume that the pretrained model is downloaded and saved to the directory `checkpoints`.

## Testing

To sample from our model, you can use `scripts/inference.py`. For example, 
```
python scripts/inference.py \
--exp_dir=result \
--checkpoint_path=checkpoints/model.pt \
--data_path=examples/sketch \
--target_path=examples/appearance \
--test_batch_size=1 \
--couple_outputs \
--test_workers=1
```
or simply run:
```
sh test.sh
```
Visualization of inputs and output:
