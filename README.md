# Ultralytics YOLO11
Ultralytics YOLO11 is the the latest version of the acclaimed real-time object detection and image segmentation model. YOLO11 is built on cutting-edge advancements in deep learning and computer vision, offering unparalleled performance in terms of speed and accuracy. Its streamlined design makes it suitable for various applications and easily adaptable to different hardware platforms, from edge devices to cloud APIs.

![image](https://github.com/user-attachments/assets/3d1e8650-3e49-49e6-bd3c-35c87b006bbd)

## Modes at a Glance
Understanding the different modes that Ultralytics YOLO11 supports is critical to getting the most out of your models:

**Train mode**: Fine-tune your model on custom or preloaded datasets.
Train mode is used for training a YOLO11 model on a custom dataset. In this mode, the model is trained using the specified dataset and hyperparameters. The training process involves optimizing the model's parameters so that it can accurately predict the classes and locations of objects in an image. Training is essential for creating models that can recognize specific objects relevant to your application.

**Val mode**: A post-training checkpoint to validate model performance.
Val mode is used for validating a YOLO11 model after it has been trained. In this mode, the model is evaluated on a validation set to measure its accuracy and generalization performance. Validation helps identify potential issues like overfitting and provides metrics such as mean Average Precision (mAP) to quantify model performance. This mode is crucial for tuning hyperparameters and improving overall model effectiveness.

**Predict mode**: Unleash the predictive power of your model on real-world data.
Predict mode is used for making predictions using a trained YOLO11 model on new images or videos. In this mode, the model is loaded from a checkpoint file, and the user can provide images or videos to perform inference. The model identifies and localizes objects in the input media, making it ready for real-world applications. Predict mode is the gateway to applying your trained model to solve practical problems.

**Export mode**: Make your model deployment-ready in various formats.
Export mode is used for converting a YOLO11 model to formats suitable for deployment across different platforms and devices. This mode transforms your PyTorch model into optimized formats like ONNX, TensorRT, or CoreML, enabling deployment in production environments. Exporting is essential for integrating your model with various software applications or hardware devices, often resulting in significant performance improvements.

**Track mode**: Extend your object detection model into real-time tracking applications.
Track mode extends YOLO11's object detection capabilities to track objects across video frames or live streams. This mode is particularly valuable for applications requiring persistent object identification, such as surveillance systems or self-driving cars. Track mode implements sophisticated algorithms like ByteTrack to maintain object identity across frames, even when objects temporarily disappear from view.

**Benchmark mode**: Analyze the speed and accuracy of your model in diverse deployment environments.
Benchmark mode profiles the speed and accuracy of various export formats for YOLO11. This mode provides comprehensive metrics on model size, accuracy (mAP50-95 for detection tasks or accuracy_top5 for classification), and inference time across different formats like ONNX, OpenVINO, and TensorRT. Benchmarking helps you select the optimal export format based on your specific requirements for speed and accuracy in your deployment environment.

# DATASET
[Dataset link](https://www.kaggle.com/datasets/trolukovich/food11-image-dataset)
Size: 1.19 GB

This dataset contains 16643 food images grouped in 11 major food categories.

## There are 3 splits in this dataset:

- Evaluation
- Training
- Validation

  <img width="960" alt="image" src="https://github.com/user-attachments/assets/cb870958-7f9f-4279-9e03-dadc96f3fb3e" />
  <img width="960" alt="image" src="https://github.com/user-attachments/assets/68390ba8-c9c5-4466-9a32-8b25afb1bbc2" />



### Each split contains 11 categories of food:

- Bread
- Dairy product
- Dessert
- Egg
- Fried food
- Meat
- Noodles-Pasta
- Rice
- Seafood
- Soup
- Vegetable-Fruit

# IMPLEMENTATION

