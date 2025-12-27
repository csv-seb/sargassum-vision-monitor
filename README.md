# Sargassum Classification Project

The Mexican Caribbean has been severely affected by the arrival of sargassum. This project aims to estimate the amount of sargassum present on beaches by analyzing beach images using image classification techniques.

The dataset was built from publicly available images collected from Facebook and Instagram. All images were stored locally and manually labeled. Image resolution and size vary, as original publication properties were preserved. Each image includes four labels: location, date, scene, and sargassum level. The level label represents the amount of sargassum and follows an ordered scale in Spanish: nada, bajo, moderado, abundante, and excesivo. The dataset is imbalanced, with a higher number of samples in the nada and bajo categories.

To solve the problem, deep learning–based image classification models were explored, including architectures such as ResNet, VGG, and GoogLeNet, to predict sargassum levels from beach images.

<img width="950" height="465" alt="image" src="https://github.com/user-attachments/assets/a1290464-d1da-478e-a173-6331b9040369" />
In this instance, the model predicted 'Abundante' with 31% confidence. The Grad-CAM heatmap reveals that the model is correctly isolating the intertidal zone. However, the lower confidence score highlights a common environmental challenge: the visual similarity between dark rocks and sargassum. To improve this, I would look into adding more 'Hard Negative' samples—images of rocky coastlines with zero sargassum—to teach the model to distinguish between mineral textures and organic biomass.
