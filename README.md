# Enhancing Biomedical Data Generation with Diffusion Mode Synthesis

![image](218504609-585bcebe-5101-4477-bdd2-3a1ba13a64a8.png)<br>
## Inspiration![image](https://user-images.githubusercontent.com/72274851/218500470-ec078b99-0a50-4b06-a2df-c09e47ecc187.png)
Biomedical research often gets stuck because of limited data. Getting access to medical images, for instance, is a bureaucratic nightmare! That's why I'm excited about diffusion models. They offer a powerful way to generate new data, and that could be a game-changer for this field.  This project is my chance to contribute and make a real difference.
<br>


## What It Does ![image](https://user-images.githubusercontent.com/72274851/218503394-b52dfcc9-0620-4f44-94f5-46a09a5cc970.png)
Imagine you're a doctor trying to diagnose a disease, but you don't have enough clear pictures to be certain. That's kind of how it is with medical imaging sometimes. There just aren't always enough high-quality images available.

This is where MNIST neural networks come in, even though they were originally designed to recognize handwritten digits. They're a type of artificial intelligence that's really good at learning patterns from images. Here's the cool part: we can train these networks on a whole bunch of existing medical images, like blood cells. By looking at all these images, the network learns the subtle differences between healthy and unhealthy cells.

Now, here's where things get exciting. This project takes that MNIST idea and builds on it.  Instead of just using existing images, we're using a special technique called a diffusion model. Think of it like taking a clear picture of a blood cell and slowly adding more and more noise until it's just static. The diffusion model can then learn how to reverse that process, starting with the static and creating a new, clear image that looks like a real blood cell!

This is like having a magic machine that can create more medical images for us to analyze.  That's where the BloodMNIST dataset comes in. It's a collection of real blood cell images that we can use to train our AI system. We resize them, split them into training and testing groups, and then feed them to the system.

The system itself is a three-pronged attack. First, the diffusion model creates new images based on the ones it's seen before. Then, a noise scheduler tells the model exactly how much noise to add or remove. Finally, a U-Net, which is another type of AI, analyzes the image and helps pinpoint the important parts, like the different types of blood cells.

By looking at how well the system performs (using things like loss curves and fancy abbreviations like FID and KID), we can see how good it is at creating realistic images and identifying the important details.  This project is basically like training a team of AI assistants to help doctors see more and diagnose better!
<br>
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
