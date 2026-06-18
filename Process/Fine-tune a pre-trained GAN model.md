# Fine-tune a pre-trained GAN model

## generative image from GAN model

📁 **WEEK 7**: [02_StyleGAN_inference.ipynb](https://git.arts.ac.uk/24006172/Critical-Coding-3-Assigments/blob/main/Week%207/02_StyleGAN_inference.ipynb)

In the Week 7 exercise, I explored the generative capabilities of a GAN model. Specifically, I utilized projection-based image inversion, where an input image is projected into the latent space of a pre-trained GAN to generate a corresponding output. Typically, when a facial image is provided as input, the output maintains facial characteristics. However, when I input a poster image instead, the model attempted to generate a face-like output based on the poster’s features.

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/7%20imagein.jpg)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/7%20out2.jpg)

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/1%20posterin.jpg)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/1%20poster%20out.jpg)


I identified the root cause of this behavior: the pre-trained GAN model I used was ffhq.pkl, which was trained specifically on facial imagery (FFHQ dataset). This observation led me to a key realization — in order to generate outputs aligned with my own visual domain (e.g., posters), I would need to train or fine-tune a GAN model on a custom dataset tailored to that aesthetic.


![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/1%20model%20choise.jpg)

## Train my own GAN model

Initially, I intended to train a StyleGAN3 model from scratch using my own dataset for image generation. However, after reviewing the official GitHub repository of StyleGAN3, I realized this approach posed several challenges.

🔗 **Alias-Free Generative Adversarial Networks (StyleGAN3)**: [GitHub](https://github.com/NVlabs/stylegan3)

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/1%20gan3.png)

First, training a full GAN model that captures a specific visual style requires a large-scale dataset, which I currently do not have access to.

Second, the official implementation has strict hardware requirements — particularly a CUDA-enabled GPU and a compatible Linux environment — which I am unable to fully support on my current setup.

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/1%20GPU.jpg)

🔗 **StyleGAN2-ADA — Official PyTorch implementation**: [GitHub](https://github.com/NVlabs/stylegan2-ada-pytorch)

As an alternative, I turned to StyleGAN2-ADA, which allows for fine-tuning a pre-trained model using a custom dataset. This approach enabled me to adapt an existing model to learn and generate images with my target visual style while using a relatively limited amount of data.
Moreover, I discovered a wide range of official pre-trained StyleGAN2 models available for download, providing a solid foundation for style-specific fine-tuning.
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/1%20GAN2%20ada.jpg)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/1%20GAN2%20pkl.jpg)



## Train own model using StyleGAN2-ADA

I found a notebook on GitHub that demonstrates how to fine-tune a model using StyleGAN2-ADA, and I plan to run it in Colab.

🔗 **StyleGAN2-ADA.ipynb-colab**: [GitHub](https://github.com/dvschultz/stylegan2-ada-pytorch)

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20nb.jpg)

Regarding the choice of pre-trained model, I selected one that features a distinct artistic design style. I believe this would help the model better learn the characteristics of Pop Art imagery and produce more stylistically coherent outputs.

🔗 **StyleGAN2 pre-trained model-WikiArt**: [GitHub](https://github.com/pbaylies/stylegan2/tree/master)

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20WikiArt.png)



I applied the method I learned in a previous assignment to download a large number of Pop Art–style images from Pinterest. My goal was to train a GAN model that could generate images in the Pop Art aesthetic.

The specific implementation can be found in another notebook.

📁 **Download image**: [Download image for training](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/Process/Download%20image%20for%20training.md)

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20imagezip.png)


The early stages of training preparation went mostly smoothly, with the exception of some issues related to the dataset not being properly recognized. One particular problem was caused by unreadable or unidentified files included in the uploaded zip archive.(🍎 always do that...)

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20popzip.jpg)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20mac%20zip.jpg)

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20train.jpg)

After successfully setting up the dataset, I began training the model. The online A100 GPU provided by Colab significantly accelerated the training process. However, due to my computer entering sleep mode, the training was interrupted midway. I then used the most recent saved checkpoint to generate an image — this became the first image generated by a model I trained myself.
I was very satisfied with the result, as the image clearly exhibits the visual characteristics of the Pop Art style, at least at this stage.

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20first%20image.jpg)

During the image generation process, I was also able to monitor the model’s output at each training stage in real time through Google Drive. It was clear that in the early stages, the model was unable to generate images in the Pop Art style, instead retaining the characteristics of the original pre-trained model. However, after extended training, the model began producing images with a distinct Pop Art aesthetic, indicating that the fine-tuning process was successful.

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20tset.jpg)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20%20first.png)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20last.png)

Since I had previously paused the training process, I replaced the original "WikiArt.pkl" model with the most recent checkpoint generated before the interruption. After resuming training, it was immediately apparent that the model was generating outputs based on the characteristics of my custom dataset right from the start.

It's a really great start.

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20change%201.png)

During the training process, I began reflecting on the entire workflow. I started to question what types of datasets are best suited for different models, and conversely, what kinds of models are more appropriate for producing specific types of outputs. I was thinking deeply about the mutual influence between data, model architecture, and the nature of the generated results.

In the process, I explored several new directions

1. Since many of the images in the Pop Art dataset contain portrait elements, I thought it would be more appropriate to use a pre-trained model based on faces like ffhq.pkl. In contrast, using models trained on WikiArt may introduce stylistic inconsistencies due to differences in subject matter and composition.
2. After fine-tuning the ffhq.pkl model using the mixed Pop Art dataset, I went one step further and replaced the entire dataset with Pop Art-style images featuring faces exclusively. This allows the face-oriented dataset and the pre-trained face-based model to be better aligned, resulting in higher quality results.

📁 **Image classification**: [Image_classifier](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/Process/Image_classifier.md)

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20change%202.png)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/11%20change%203.png)

I ultimately decided to fine-tune the face-based pre-trained model ffhq.pkl using my curated dataset of Pop Art portraits. My goal is to combine the strong facial generation capabilities of the original model with the distinct visual style of Pop Art. Through this approach, I hope the newly trained model will not only adopt Pop Art aesthetics but also preserve the proportional integrity of facial structures in the generated images.
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/111%20last.jpg)

I will continue training this model until the final submission.

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/111%20training.png)

By continuously monitoring the model’s generative performance during training, I can clearly observe a gradual improvement in its ability to produce images with Pop Art visual characteristics.

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/111%2001.png)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/111%2002.png)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/111%2003.png)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/111%2004.png)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/111%2005.png)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/111%2006.png)


❓❓❓ From this stage of model training, I noticed that many irregular horizontal shapes were generated around the faces in the images. 

Based on my analysis, this may be caused by the mismatch between the size of my training dataset (512×512) and the pre-trained model ffhq.pkl (1024×1024), which could have led to stretched or distorted outputs. 

Another possibility is that due to too little training, the training set is now not fully fused with the ffhq.pkl pre-trained model, because after checking the previous training with the WikiArt.pkl model, a similar problem occurred. Perhaps this is due to insufficient training time.

(However, the exact cause is still uncertain, and I plan to revisit this observation after further training progress for a more thorough comparison.)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/111.%20wenti.jpg)
![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/111%20wenti2.png)

