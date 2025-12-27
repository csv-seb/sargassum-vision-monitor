# Sargassum Classification Project

The Mexican Caribbean has been severely affected by the arrival of sargassum. This project aims to estimate the amount of sargassum present on beaches by analyzing beach images using image classification techniques.

The dataset was built from publicly available images collected from Facebook and Instagram. All images were stored locally and manually labeled. Image resolution and size vary, as original publication properties were preserved. Each image includes four labels: location, date, scene, and sargassum level. The level label represents the amount of sargassum and follows an ordered scale in Spanish: nada, bajo, moderado, abundante, and excesivo. The dataset is imbalanced, with a higher number of samples in the nada and bajo categories.

To solve the problem, deep learning–based image classification models were explored, including architectures such as ResNet, VGG, and GoogLeNet, to predict sargassum levels from beach images.
