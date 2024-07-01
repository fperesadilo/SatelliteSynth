# SatelliteSynth
To implement Stable Diffusion for generating synthetic satellite images using the Netherlands Space Office dataset, I followed a structured approach.

## Data Preparation
I started by collecting a diverse dataset of satellite images, capturing various weather conditions, seasons, and geographical features. Preprocessing involved resizing all images to 256x256 pixels and normalizing pixel values to the range [0, 1], which enhances model performance by ensuring numerical stability.

## Model Selection and Architecture
I selected a Stable Diffusion-based architecture, utilizing a modified U-Net as the core network. Diffusion models are adept at generating high-quality synthetic images by refining noise into coherent images through an iterative diffusion process.

## Training the Model
Training involved adding Gaussian noise to the satellite images and teaching the model to reverse this process, transforming noisy images back into their original form. I used a combination of mean squared error (MSE) and perceptual loss functions to guide the model, balancing pixel accuracy with high-level feature coherence. The model was trained on a powerful GPU setup with a batch size of 16 for 200 epochs, with dynamic learning rate adjustments.

## Image Generation
Post-training, I generated synthetic images by inputting random noise into the model, which refined it through the learned diffusion process. The generated images were visually inspected and compared against the original dataset to ensure quality and diversity.

## Post-processing and Evaluation
Post-processing included denoising and fine-tuning the images to remove artifacts. Quantitative evaluation using metrics like the Frechet Inception Distance (FID) validated the model’s performance by comparing synthetic images to real ones.

This structured approach enabled me to leverage Stable Diffusion effectively, producing high-quality, diverse synthetic satellite images that faithfully represented the characteristics of the original dataset.
