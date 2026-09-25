Developed a conditional Generative Adversarial Network (GAN) to generate synthetic 28×28 grayscale aerial images from the Overhead-MNIST dataset, covering Stadium and Oil Gas Field classes.

Key work:
- Performed exploratory analysis and preprocessing of the Overhead-MNIST dataset, including image normalization and conditional class labeling for Stadium and Oil Gas Field images.
- Built a baseline conditional GAN using Dense layers for both the Generator and Discriminator, with label embeddings to control the generated image class.
- Trained the baseline GAN for 50 epochs using the Adam optimizer with a learning rate of 2×10⁻⁴ and β₁ = 0.5.
- Evaluated generated image quality using Fréchet Inception Distance (FID), with the baseline GAN achieving a FID of 387.87 on the test set.
- Improved the GAN architecture by replacing Dense-based image generation with a DCGAN-style convolutional architecture using Conv2DTranspose, Batch Normalization, and convolutional refinement layers.
- Improved the Discriminator using Conv2D layers, SpatialDropout2D, LeakyReLU activations, and spatial label conditioning through label maps.
- Applied label smoothing and asymmetric learning rates to improve GAN training stability and prevent the Discriminator from dominating the Generator.
- Performed manual hyperparameter tuning across three configurations by varying Discriminator learning rate, Generator learning rate, label smoothing, and batch size. The best configuration used d_lr=1×10⁻⁴, g_lr=2×10⁻⁴, label smoothing=0.90, and batch size=64.
- Trained the final Improved GAN for 300 epochs using the selected configuration.
- Achieved a test-set FID of 232.11, reducing FID by 155.76 points compared with the baseline and demonstrating substantially improved generated image quality and similarity to the real image distribution.

Dataset: https://www.kaggle.com/datasets/datamunge/overheadmnist/data
