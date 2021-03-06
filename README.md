# CT image denoising with deep learning
-----------

## 01. A deep convolutional neural network using directional wavelets for low-dose X-ray CT reconstruction (KAIST-net).
(https://aapm.onlinelibrary.wiley.com/doi/epdf/10.1002/mp.12344)
### **Model**
![KAISTNET](https://github.com/SSinyu/CT_DENOISING/blob/master/img/%5B01%5DKAISTNET.PNG)
- This method works on wavelet coefficients of low-dose CT images.
- Network contains 24 convolution layers.
### **Dataset**
- AAPM-Mayo Clinic Low-Dose CT Grand Challenge (only abdominal CT images).
  - 512x512, 10 patients, 5743 slices.
  - use a 55x55 patches.

--------

## 02. Low-dose CT via Convolutional Neural Network.  
(https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5330597/pdf/679.pdf)
### **Model**
- Network use only 3 conoluional layers (Conv - ReLU - Conv - ReLU - Conv).
### **Dataset**
- TCIA(The Cancer Imaging Archive) normal-dose CT images.
  - 256x256, 165 patients, 7015 slices.
  - impose Poisson noise into normal-dose sinogram.
  - use a 33x33 patches.

--------

## 03. Improving Low-Dose CT Image Using Residual Convolutional Network.
(https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8082505)
### **Model**
![ResCNN](https://github.com/SSinyu/CT_DENOISING/blob/master/img/%5B03%5DResidual_CNN.PNG)
- 2D residual convolution net.
- 3D residual convolution net (take into account the spatial continuity of tissues).
### **Dataset**
- AAPM-Mayo Clinic Low-Dose CT Grand Challenge.
  - 512x512, 10 patients, 5080 slices.
  - use a 44x44 patches(2D), 44x44x24 patches(3D).

--------

## 04. CT Image Denoising with Perceptive Deep Neural Networks
.
(https://arxiv.org/pdf/1702.07019.pdf)
### **Model**
![PerDNN](https://github.com/SSinyu/CT_DENOISING/blob/master/img/%5B04%5DPerceptive_DNN.PNG)
- Compare the denoised output against the ground truth in another high-dimensional feature space (from VGG).
### **Dataset**
- cadaver CT image dataset collected at Massachusetts General Hospital (MGH).

--------

## 05. Low-Dose CT with a Residual Encoder-Decoder Convolutional Neural Network (RED-CNN).
(https://arxiv.org/ftp/arxiv/papers/1702/1702.00288.pdf)
### **Model**
![REDCNN](https://github.com/SSinyu/CT_DENOISING/blob/master/img/%5B05%5DRED-CNN.PNG)
- Incoporated a deconvolution network and shortcut connections into a CNN model.
### **Dataset**
- NBIA(Natioanl Biomedical Imaging Archive) normal-dose CT images.
  - 256x256, 165 patients, 7015 slices.
  - adding Poisson noise into the sinogram simulated from the normal-dose images.
- AAPM-Mayo Clinic Low-Dose CT Grand Challenge.
  - 512x512, 10 patients, 2378 slices.
  - use a 55x55 patches.

--------

## 06. Generative adversarial networks for noise reduction in low-dose CT.
(https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7934380)
### **Model**
![GAN](https://github.com/SSinyu/CT_DENOISING/blob/master/img/%5B06%5DGAN.PNG)
- Generator transforms the low-dose CT image into noise reduced image.
- Discriminator determines whether the input is a real routine-dose image or not.
### **Dataset**
- Phantom CT scans
  - An anthropomorphic thorax phantom (QRM anthropomorphic thorax phantom)
  - voltage of 120 kVp. 50mAs(routine-dose), 10mAs(low-dose).
- Cardiac CT scan (28 patients)
  - voltage of 120 kVp. 50~60mAs(routine-dose), 10~12mAs(low-dose).

--------

## 07. Structure-sensitive Multi-scale Deep Neural Network for Low-Dose CT Denoising.
(https://arxiv.org/pdf/1805.00587.pdf)
### **Model**
![SMGAN](https://github.com/SSinyu/CT_DENOISING/blob/master/img/%5B07%5DSMGAN.PNG)
- (Part 1). Generator consist of eight 3D convolutional (Conv) layers.
- (Part 2). Calculate patch-wise error between the 3D output and the 3D NDCT images.
![SMGAN_loss](https://github.com/SSinyu/CT_DENOISING/blob/master/img/%5B07%5Dloss.PNG)
- (Part 3). Discriminator distinguishes between two images.
### **Dataset**
- AAPM-Mayo Clinic Low-Dose CT Grand Challenge.
  - 512x512, 10 patients, 2378 slices.
  - use a 80x80x11 patches.

--------

## 08. Low Dose CT Image Denoising Using a Generative Adversarial Network with Wasserstein Distance and Perceptual Loss
(https://arxiv.org/pdf/1708.00961.pdf)
### **Model**
![WGAN](https://github.com/SSinyu/CT_DENOISING/blob/master/img/%5B08%5DWGAN.PNG)
- GAN with Wasserstein distance.
- (Part 2). Comparing the perceptual feature of a denoised output against those of the ground truth in an established feature space.
### **Dataset**
- AAPM-Mayo Clinic Low-Dose CT Grand Challenge.
  - 512x512, 10 patients, 4000 slices.
  - use a 64x64 patches.

--------

## 09. Sharpness-aware Low Dose CT Denoising Using Conditional Generative Adversarial Network.
(https://arxiv.org/pdf/1708.06453.pdf)
### **Model**
![SAGAN](https://github.com/SSinyu/CT_DENOISING/blob/master/img/%5B09%5DSAGAN.PNG)
- Sharpness detection network : generate a similar sharpness map as closs as to real CT.
![SAGAN_loss](https://github.com/SSinyu/CT_DENOISING/blob/master/img/%5B09%5DSAGNA_loss.PNG)
### **Dataset**
- NBIA(Natioanl Biomedical Imaging Archive) normal-dose CT images.
  - 512x512, 239 slices.
  - adding Poisson + normally Gaussian noise.
  - use a 256x256 patches (sampled from the 4 corners and centre).
- Deceased piglet CT
  - voltage of 100 kVp. 300mAs(full-dose) ~ 15mAs(low-dose).
- Phantom CT scans
  - voltage of 120 kVp. 300mAs(full-dose) ~ 15mAs(low-dose).
- Data Science Bowl 2017 
  - Detect lung cancer from LDCTs.

--------

## 10. 3D Convolutional Encoder-Decoder Network for Low-Dose CT via Transfer Learning from a 2D Trained Network.
(https://arxiv.org/pdf/1802.05656.pdf)
### **Model**
![Transfer](https://github.com/SSinyu/CT_DENOISING/blob/master/img/%5B10%5DTransfer.PNG)
- Concatenation of feature-maps from the two sides of the conveying-path.
- Learn the 2D model first, and use it to initialize the 3D network. This transfer learning shows much faster convergence and better performance.
### **Dataset**
- AAPM-Mayo Clinic Low-Dose CT Grand Challenge.
  - 512x512, 10 patients.
  - use a 64x64 patches.

--------

## 11. Cycle Consistent Adversarial Denoising Network for Multiphase Coronary CT Angiography
(https://arxiv.org/abs/1806.09748)
### **Model**
![CYCLEGAN](https://github.com/SSinyu/CT_DENOISING/blob/master/img/%5B11%5DCYCLEGAN.PNG)
- In coronary CTA, the images at the low-dose and routine-dose phases do not match each other exactly due to the cardiac motion.
- Two generator denotes the mapping form low-dose to routine-dose image and from routine-dose to low-dose image, two adversarial discriminators distinguish between input images and synthesized images from the generators
- Using cycle-consistent adversarial denoising network, learn the mapping between the low and routine dose cardiac phases.
### **Dataset**
- 50 CT scans of mitral valve prolapse patients, and 50 CT scans of coronary artery disease patients.
  - use a 56x56 patches.
- AAPM-Mayo Clinic Low-Dose CT Grand Challenge.
