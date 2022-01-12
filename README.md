# VRDL_HW4

## SuperResolution

I've tried two models. 

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
