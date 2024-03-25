# Enhancing Biomedical Data Generation with Diffusion Mode Synthesis

![image](218504609-585bcebe-5101-4477-bdd2-3a1ba13a64a8.png)<br>
## Inspiration![image](https://user-images.githubusercontent.com/72274851/218500470-ec078b99-0a50-4b06-a2df-c09e47ecc187.png)

Image synthesis on medical images holds immense potential for generating more data to address biomedical problems. 
However, legal and technical limitations often hinder this process. This project explores Diffusion Models, a powerful approach, to overcome these limitations and contribute to advancements in medical data generation.
<br>


## What It Does ![image](https://user-images.githubusercontent.com/72274851/218503394-b52dfcc9-0620-4f44-94f5-46a09a5cc970.png)

This project implements a Diffusion Model for image synthesis on medical datasets. 
1. **Data Augmentation:** Enhances model performance by diversifying training data.
2. **Noise Scheduler:** Dynamically applies noise during training, improving model resilience and preventing overfitting.
3. **U-Net Architecture:** Effective for image segmentation tasks, accurately capturing intricate patterns.
4. **Wrapper:** Encapsulates noise scheduler and U-Net, streamlining integration and workflow.
5. **BloodMNIST Dataset:** Contains images of blood cells, suitable for medical image analysis.
6. **Framework Benefits:** Improves model robustness, generalization, and adaptability to real-world scenarios.<br>
![image](qualitative_result.png)


## How We built it ![image](https://user-images.githubusercontent.com/72274851/218502434-f6e66043-0db0-4f85-b7f4-f33b2d33df1f.png)

**1. Importing the Libraries:**
Begin by importing necessary libraries such as TensorFlow or PyTorch for deep learning, along with libraries for data manipulation and visualization such as NumPy, pandas, and Matplotlib and other necessary libraries.

**2. Dataset Preparation:**
Load the BloodMNIST dataset, containing images of normal blood cells from individuals without diseases. The dataset is organized into 8 classes and divided into training, validation, and test sets. Images are preprocessed by center-cropping and resizing to 28x28 pixels.

**3. Diffusion Model Architecture with Noise Scheduler:**
Utilize the diffusion model architecture along with a noise scheduler. This scheduler dynamically adjusts the level and type of noise added to input images during training. The U-Net architecture is employed within this framework to perform image segmentation tasks. The wrapper facilitates the integration of the noise scheduler and U-Net architecture for efficient data augmentation. During training, the model learns to denoise and segment blood cell images, improving its robustness and generalization.

**4. Performance Evaluation:**
After training the model, evaluate its performance by plotting various metrics. 
Loss curves depict the training progress and convergence. 
FID (Fréchet Inception Distance) and KID (Kernel Inception Distance) curves measure the similarity between generated and real images, indicating the quality of generated samples.
 These curves provide insights into the model's performance and its ability to produce realistic and accurate segmentations of blood cell images.

By following these steps, a comprehensive framework for data augmentation, training, and evaluation of the BloodMNIST dataset using diffusion model architecture, noise scheduler, U-Net, and wrapper is built.

<br>
![image](loss_curve.png)
<br>

## What I learned ![image](https://user-images.githubusercontent.com/72274851/218499685-e8d445fc-e35e-4ab5-abc1-c32462592603.png)


This project provided valuable insights into:

* Building application using intel oneDAL:The Intel oneAPI Data Analytics Library (oneDAL) contributes to the acceleration of big data analysis by providing highly optimised algorithmic building blocks for all phases of data analytics (preprocessing, transformation, analysis, modelling, validation, and decision making) in batch, online, and distributed processing modes of computation.The library optimizes data ingestion along with algorithmic computation to increase throughput and scalability.
* The capabilities of Diffusion Models for biomedical image synthesis.
* The effectiveness of U-Net architecture in image restoration tasks.
* The importance of quantitative metrics (FID and KID) to evaluate model performance.
