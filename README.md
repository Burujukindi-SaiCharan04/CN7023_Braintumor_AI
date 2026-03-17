# CN7023_Braintumor_AI

# Explainable Deep Learning for Brain Tumour Classification in MRI Images using Grad-CAM

# Student Name: Sai Charan Burujukindi
# Student ID: 3018871


# 1. Project Overview

This project presents an explainable deep learning framework for classifying brain tumours using MRI images. The proposed system combines high-performance convolutional neural networks with interpretability using Grad-CAM. The model classifies MRI scans into four categories: glioma, meningioma, pituitary tumour, and no tumour. Explainability is critical in medical AI to ensure transparency and trust in clinical decision-making (Selvaraju et al., 2017).

# 2. Dataset Description

The dataset used is the Brain Tumor MRI dataset obtained from Kaggle. It contains a total of 7200 images, with 5600 training images and 1600 testing images. Each class (glioma, meningioma, pituitary, and no tumour) contains 1800 images, ensuring a perfectly balanced dataset. The images are primarily of size 512×512 pixels, and all are stored in JPG format.

# Data Source Link :
# https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset

# 3. Data Preprocessing

The preprocessing pipeline includes resizing all images to 224×224 pixels, normalizing pixel values between 0 and 1, and batching with a size of 32. Data augmentation techniques such as rotation (20°), zoom (10%), horizontal flipping, and shifting were applied to improve generalization and reduce overfitting (Shorten and Khoshgoftaar, 2019).

# 4. Dataset Analysis

Exploratory data analysis confirmed that the dataset is fully balanced, with each class contributing 25% (1800 images) of the total data. Image analysis revealed that 4129 images are RGB (3 channels) and 3068 images are grayscale (1 channel). Most images are standardized at 512×512 resolution, though some variation exists. This diversity improves model robustness.

# 5. Model Architecture

The model uses transfer learning based on the InceptionV3 architecture, which is pretrained on ImageNet. Additional layers such as Global Average Pooling, Dense layers, Batch Normalization, and Dropout (0.5) were added to enhance classification performance. Transfer learning improves feature extraction and reduces training time (Szegedy et al., 2016).

# 6. Training Strategy

The model was trained using the Adam optimizer with a learning rate of 0.001 and batch size of 32. Mixed precision training was used to improve computational efficiency. EarlyStopping (patience = 5), ReduceLROnPlateau, and ModelCheckpoint were applied to optimize training performance and prevent overfitting (Kingma and Ba, 2015).

# 7. Explainability using Grad-CAM

Grad-CAM was used to visualize important regions in MRI images that influence model predictions. The heatmaps generated highlight tumour regions, confirming that the model focuses on medically relevant areas. This enhances trust and interpretability in deep learning systems (Selvaraju et al., 2017).

# 8. Results and Performance

The model achieved strong performance across all evaluation metrics. The final results are as follows:

Training Accuracy: 98.7%

Validation Accuracy: 97.9%

Test Accuracy: 97.5%

Precision: 97.6%

Recall: 97.4%

F1-Score: 97.5%

ROC-AUC Score: 0.99

The confusion matrix shows that the model correctly classifies the majority of MRI images with very few misclassifications between tumour types. Grad-CAM visualizations further confirm that the model accurately identifies tumour regions, validating its decision-making process.

# 9. Key Findings

The use of transfer learning significantly improved classification accuracy while reducing training time. Data augmentation increased model robustness and prevented overfitting. The balanced dataset ensured uniform performance across all classes. Grad-CAM provided clear visual explanations, making the model suitable for real-world medical applications (Ribeiro et al., 2016).

# 10. Conclusion

This project successfully demonstrates an explainable deep learning model for brain tumour classification. The integration of Grad-CAM ensures both high accuracy and interpretability, which are essential in healthcare applications. The model achieved over 97% accuracy, indicating strong potential for assisting radiologists in diagnosis.

# 11. How to Run the Project

Install required libraries such as TensorFlow, Keras, OpenCV, and Scikit-learn. Download the dataset using KaggleHub or manually. Run the notebook step-by-step to preprocess the data, train the model, and generate Grad-CAM visualizations.


# 12. References 

Kingma, D. P., and Ba, J. (2015). Adam: A method for stochastic optimization. International Conference on Learning Representations.

Ribeiro, M. T., Singh, S., and Guestrin, C. (2016). “Why should I trust you?” Explaining the predictions of any classifier. Proceedings of the 22nd ACM SIGKDD Conference.

Selvaraju, R. R., Cogswell, M., Das, A., Vedantam, R., Parikh, D., and Batra, D. (2017). Grad-CAM: Visual explanations from deep networks via gradient-based localization. Proceedings of the IEEE International Conference on Computer Vision.

Shorten, C., and Khoshgoftaar, T. M. (2019). A survey on image data augmentation for deep learning. Journal of Big Data, 6(1), 1–48.

Szegedy, C., Vanhoucke, V., Ioffe, S., Shlens, J., and Wojna, Z. (2016). Rethinking the Inception architecture for computer vision. Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition.
