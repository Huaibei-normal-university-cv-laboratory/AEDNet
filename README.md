# AEDNet
Our paper is currently under submission, and detailed data information will be made public after its publication

## 1. Download pre-trained swin transformer model (Swin-T)
- Put pretrained Swin-T into folder "pretrained_ckpt/"

## 2. Environment

- Please For details of our environment, please refer to "environment.yml"

## 3. Train/Test

- Run training scripts on synapse datasets. The batch we use is 24. If the GPU memory is sufficient, the bacth size can be increased to 48 or 96. We do not recommend using multi card operation.

- Train

```bash
python train.py --dataset Synapse --cfg configs/aednet_base_synapse.yaml --root_path <your_datapath> --max_epochs 150 --output_dir ./trained_out --img_size 224 --base_lr 0.05 --batch_size 24
```

- Test 

```bash
python test.py --dataset Synapse --cfg configs/aednet_base_synapse.yaml --volume_path <your_datapath> --max_epochs 150 --output_dir ./trained_out --img_size 224 --base_lr 0.05 --batch_size 24
```

- Codes

To reproduce the segmentation results presented in this paper, we found that different GPU types can yield different outcomes. In our code, we set certain random seeds, so the results should be similar when inferring on the same type of GPU; however, we cannot rule out errors due to floating-point calculations. If the training does not produce the same segmentation results as reported in the paper, we recommend tuning the parameters. Additionally, the GPU type we used for this work is the Nvidia A30.

## References
* [Swin-Unet](https://github.com/HuCaoFighting/Swin-Unet)
* [SwinTransformer](https://github.com/microsoft/Swin-Transformer)
