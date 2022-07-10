# VRDL_HW4 (SuperResolution)

## Reference：

1.	Unsupervised method－ZSSR：https://github.com/assafshocher/ZSSR

Most super resolution algorithms need to be trained on a specific dataset to obtain the target model. The ZeroShotSR algorithm requires neither prior image samples nor prior training, it uses the internal repetition information of a single image to train a small image-specific CNN during testing.

2.	Supervised method－SwinIR：https://github.com/JingyunLiang/SwinIR, https://github.com/cszn/KAIR

SwinIR is method that use transformer to restore image. The experimental results show that the performance of SwinIR is 0.14-0.45dB higher than the current sota method, and the parameter quantity is also reduced by 67%.

## Brief introduction： 

Super Resolution refers to reconstructing a corresponding high-resolution image from an observed low-resolution image by means of software or hardware. Two commonly used indicators for quantitative evaluation of SR quality are PSNR (Peak Signal-to-Noise Ratio) and SSIM (Structure Similarity Index). The higher the two values, the closer the pixel value of the reconstruction result is to the standard. The indicator for evaluation of this homework is PSNR, details are as follows. 

The research process of image super-resolution reconstruction based on deep learning is as follows. First, find a set of original images Image1. Second, reduce the resolution of this group of pictures to a group of images Image2, and then reconstruct Image2 super-resolution to Image3 through various neural network structures (Image3 has the same resolution as Image1). Compare Image1 and Image3 through PSNR or other methods, and verify the effect of super-resolution reconstruction. Adjust the node model and parameters in the neural network according to the effect. Eventually, execute the process repeatedly until the result of the fourth step comparison is satisfactory.

## 1. Supervised method－SwinIR

weights：https://drive.google.com/drive/folders/1YmEy9Cx0abPUg5aDkjdOatqSRO0KMxeF?usp=sharing

### Usage

Change the main_test_swinir.py from the clone file to main_test_swinir.py on my GitHub.

Put the testing images in the <SwinIR path>/testsets/test file.

Rub the classical super resolution.

Upscale the testing images to 3.

    !python main_test_swinir.py --task classical_sr --scale 3 --training_patch_size 48 --model_path superresolution/swinir_sr_classical_patch48_x3/models/25000_G.pth --folder_lq '/home/wschenst06g/Ming/MMSE_global/dodo/KAIR/testsets/test' --folder_gt testsets/test


  
## 2. Unsupervised method－ZSSR. 

weights（1.pkl - 13.pkl）：https://drive.google.com/drive/folders/1-6Cj-yDXON2mbNgLITit8UtHJU2hZhmd?usp=sharing
    
### Usage

Change the ZSSR.py from the clone file to ZSSR.py on my GitHub.

    !pip install GPUtil
    !python run_ZSSR.py



## Results

The SwinIR model removes severe noise interference and preserves high frequency image details for sharper edges and more natural textures. The ZSSR model also reconstruct clear image, but we can see that it’s still blurrier than the SwinIR model. The testing set of this homework is somehow ideal images. That is to say, compared with other pre- training-based methods, ZSSR can really achieve comparable results in ideal cases, and better results than pre-training methods in non-ideal cases.
The final testing PSNR of ZSSR model is roughly 27.8, and the testing PSNR of SwinIR model is roughly 28.2.

### SwinIR

<img width="372" alt="image" src="https://user-images.githubusercontent.com/77607182/149051398-7dcff342-1db7-4c6c-b127-48bba26a42bc.png">
    
### ZSSR

<img width="372" alt="image" src="https://user-images.githubusercontent.com/77607182/149051408-32e6bc5d-d6af-4b18-88ba-be1ba35db51e.png">
