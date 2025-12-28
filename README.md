# Sargassum Influx Classification: An AI Approach to Environmental Monitoring

## Developed for the UNAM 'Macroentrenamiento en IA (MeIA 2025)' Kaggle Competition (June 2025)

### Project Overview

The Mexican Caribbean faces recurring sargassum arrivals that severely impact tourism, local ecosystems, and the built environment. This project focuses on Environmental Computer Vision, aiming to automatically estimate sargassum levels from beach imagery using Deep Learning. 
By leveraging Transfer Learning and Explainable AI (XAI), this system provides a scalable solution for local authorities and AECO (Architecture, Engineering, Construction, and Operations) firms to optimize beach cleanup logistics and resource allocation. 
The task is a multiclass, ordinal classification problem featuring five levels of sargassum presence: 
- Nada (None)
- Bajo (Low)
- Moderado (Moderate)
- Abundante (High)
- Excesivo (Very High)

### Dataset & Origin
- Source: Dataset and baseline code provided by the UNAM 'MeIA 2025' instructional team.
- Input: RGB beach images sourced from social media (Facebook/Instagram).
- Challenges: Significant class imbalance (majority "Nada/Bajo" samples) and varying image resolutions.
- Split: Stratified sampling used to maintain label distribution across Training and Validation sets.

### Technical Implementation
#### 1. Model Architectures
Two distinct CNN architectures were benchmarked to find the balance between edge-deployment efficiency and high-accuracy classification:
- MobileNetV2 (Baseline) - Efficiency for mobile devices.
- EfficientNet-B2 (Final Model) - Higher robustness.

### Advanced Training Strategy
To improve the baseline results provided by the instructors, I implemented several advanced techniques:
- Loss Function: Switched to Focal Loss to penalize the model more heavily for misclassifying the rarer, high-impact categories ("Abundante/Excesivo").
- Optimization: Utilized AdamW with a ReduceLROnPlateau scheduler to dynamically adjust learning rates as training converged.
- Data Augmentation: Applied RandomResizedCrop, ColorJitter, and RandomPerspective to simulate different weather conditions and camera angles.
- Checkpointing: Integrated a persistent saving system in Google Colab to preserve the best model weights based on Validation F1-score.

### Interpretability
As a researcher with a background in Visual Arts, ensuring model transparency was a priority. I implemented Grad-CAM (Gradient-weighted Class Activation Mapping) to visualize the model's "attention."

#### Key Insight: 
Analysis of the heatmaps verified that the model correctly ignores "noise" (sky, deep water) and focuses its activation on the patterns of the shoreline where sargassum typically accumulates. In this instance, the model predicted 'Abundante' with 31% confidence. The lower confidence score highlights a common environmental challenge: the visual similarity between dark rocks and sargassum. To improve this, I would look into adding more 'Hard Negative' samples—images of rocky coastlines with zero sargassum—to teach the model to distinguish between mineral textures and organic biomass.

<img width="950" height="465" alt="image" src="https://github.com/user-attachments/assets/a1290464-d1da-478e-a173-6331b9040369" />
 


### Results & Output
- submission.csv: Predictions generated for the Kaggle test set.
- best_model.pth: Optimized weights for deployment.
- Classification Report: Detailed breakdown of Precision, Recall, and F1-score per class, identifying specific areas for future dataset expansion.

### Tech Stack
- Core: Python, PyTorch, Torchvision
- Analytics: Scikit-learn, Pandas, NumPy
- Visualization: Matplotlib, OpenCV, PIL
- Platform: Google Colab (GPU-accelerated training)

Author: Sebastian Méndez



