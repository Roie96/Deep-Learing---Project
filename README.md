# Colorizing Grayscale Images Using Generative Adversarial Networks

This project aims to colorize grayscale images using different models of Generative Adversarial Networks (GANs). After experimenting with various approaches, we selected the GAN-L1 model due to its superior performance.

## Models and Notebooks

The submission includes three notebooks:
1. **WGAN**
2. **GAN-L1**
3. **GAN-MSE**

We initially focused on the WGAN model but found it did not meet our expectations. After extensive training, we chose the GAN-L1 model for its better performance, while GAN-MSE is discussed for comparative purposes.

---

## Project Overview

### Dataset

We used the Flower-102 dataset by Maria-Elena Nilsback and Andrew Zisserman for training and testing.

### Architecture

#### Generator - U-Net Architecture
- **Input Layer:** Accepts 1-channel grayscale images.
- **Downsampling Path:** Sequential VGG blocks, increasing complexity from 64 to 1024 channels.
- **Upsampling Path:** Mirrors the downsampling structure, restoring image dimensions.
- **Output Layer:** Converts processed features into a 3-channel color image.

#### Discriminator - CNN
- **Layers:** Sequential VGG blocks with Instance Normalization and LeakyReLU, increasing from 64 to 1024 channels.
- **Final Layer:** Outputs a single value to determine real or fake images.

---

### Training

- **Optimizer:** Adam optimizer is used for all U-Net models.
- **Epochs:** Trained for 350 epochs, with the discriminator and generator trained iteratively.

### Loss Functions

- **GAN + MSE:** Combined MSE Loss and GAN Loss.
- **GAN + L1:** Combined L1 Loss (Mean Absolute Error) and GAN Loss. Chosen for its better performance in producing sharper and clearer images.

### Results

- **GAN + MSE:** Stable training with consistent loss reduction and image quality improvement![Screenshot 2024-06-01 at 15 37 14](https://github.com/Roie96/Deep-Learing---Project/assets/100276577/177250a8-eb92-476e-b18a-deff86b09fa5)

- **GAN + L1:** Better stability and realism in output images compared to GAN + MSE.![Screenshot 2024-06-01 at 15 39 58](https://github.com/Roie96/Deep-Learing---Project/assets/100276577/b575a6ec-9d14-4d27-ba7d-3a78ea08f0a4)


---

### WGAN - Bonus

We explored the WGAN approach initially but moved away due to the extensive computational resources and long training time required.

---

## Running the Model

1. **Upload the GAN-L1 notebook to Google Colab.**
2. **Download the model from [this link](https://drive.google.com/file/d/1aHGpMl5VdSlpQUCmUJnsR8ONWL2k_MOr/view?usp=share_link).**
3. **Upload the model to your Google Drive.**
4. **Copy the model path from your Google Drive and paste it in the specified line in the notebook.**
5. **Run the first and second blocks in the notebook.**
6. **Run the final block to generate results.**

---

