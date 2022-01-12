# VRDL_HW4

## SuperResolution

I've tried two models. 

## 1. Supervised model－SwinIR


## 2. Unsupervised model－ZSSR. 

weights（1.pkl - 13.pkl）：https://drive.google.com/drive/folders/1-6Cj-yDXON2mbNgLITit8UtHJU2hZhmd?usp=sharing








The SwinIR model removes severe noise interference and preserves high frequency image details for sharper edges and more natural textures. The ZSSR model also reconstruct clear image, but we can see that it’s still blurrier than the SwinIR model. The testing set of this homework is somehow ideal images. That is to say, compared with other pre- training-based methods, ZSSR can really achieve comparable results in ideal cases, and better results than pre-training methods in non-ideal cases.
The final testing PSNR of ZSSR model is roughly 27.8, and the testing PSNR of SwinIR model is roughly 28.2.
