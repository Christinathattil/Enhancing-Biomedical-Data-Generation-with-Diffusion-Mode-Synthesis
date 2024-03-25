# Enhancing Biomedical Data Generation with Diffusion Mode Synthesis

![image](218504609-585bcebe-5101-4477-bdd2-3a1ba13a64a8.png)<br>
## Inspiration![image](https://user-images.githubusercontent.com/72274851/218500470-ec078b99-0a50-4b06-a2df-c09e47ecc187.png)
The inspiration for this project springs from the imperative need to advance solutions for data limitations in biomedical problems. With the intricate legal and technical complexities associated with obtaining medical imagery data, the innovation and potential of the diffusion model stood out as a promising avenue. The aspiration to contribute to this critical domain sparked the choice of this project.
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
We initiate the process by importing essential libraries for deep learning such as TensorFlow or PyTorch, along with libraries for data manipulation (e.g., NumPy, pandas) and visualization (e.g., Matplotlib).

**2. Dataset Preparation:**
We load the BloodMNIST dataset, which consists of images of normal blood cells from healthy individuals. The dataset is divided into training, validation, and test sets with a split ratio of 7:1:2. Initially, the images with a resolution of 3×360×363 pixels are center-cropped to 3×200×200 pixels, and then resized to 3×28×28 pixels to match the input size required by the model.

**3. Diffusion Model Architecture with Noise Scheduler:**
The diffusion model architecture is implemented, which involves a forward process applying Gaussian noise to an image guided by a noise scheduler. This process is followed by a U-Net-based backward process that restores the image to its original state. The noise scheduler dynamically adjusts the level and type of noise added during training to enhance model robustness and generalization. The U-Net architecture within this framework aids in image segmentation tasks, effectively capturing intricate patterns in the blood cell images. A wrapper is utilized to integrate the noise scheduler and U-Net architecture, facilitating data augmentation, training, and testing of the BloodMNIST dataset.

**4. Performance Evaluation:**
The performance of the trained model is evaluated by plotting various curves. Loss curves illustrate the convergence and training progress of the model. FID (Fréchet Inception Distance) and KID (Kernel Inception Distance) curves measure the similarity between generated and real images, providing insights into the quality of generated samples and the model's performance in accurately segmenting blood cell images.

Through these steps, we build a comprehensive framework for data augmentation, training, and evaluation of the BloodMNIST dataset using diffusion model architecture, noise scheduler, U-Net, and wrapper.<br>

![image](loss_curve.png)
<br>
![image](FrechetInceptionDistance.png)
<br>
![image](KernalInceptionDistance.png)
## What I learned ![image](https://user-images.githubusercontent.com/72274851/218499685-e8d445fc-e35e-4ab5-abc1-c32462592603.png)


This project provided valuable insights into:

* Building application using intel oneDAL:The Intel oneAPI Data Analytics Library (oneDAL) contributes to the acceleration of big data analysis by providing highly optimised algorithmic building blocks for all phases of data analytics (preprocessing, transformation, analysis, modelling, validation, and decision making) in batch, online, and distributed processing modes of computation.The library optimizes data ingestion along with algorithmic computation to increase throughput and scalability.
* The capabilities of Diffusion Models for biomedical image synthesis.
* The effectiveness of U-Net architecture in image restoration tasks.
* The importance of quantitative metrics (FID and KID) to evaluate model performance.
