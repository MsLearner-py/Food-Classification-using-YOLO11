![Visitor Count](https://profile-counter.glitch.me/vyasdeepti/count.svg)

# Objective: To classify food images in different food categories using YOLO11 model 🍎🥙🍅🍕🍔🍩

This repository demonstrates food image classification using the YOLOv1 (You Only Look Once) object detection algorithm. The project provides a pipeline for training, evaluating, and running inference on food images to detect and classify food items.


## Table of Contents

1. [Objective](#objective-to-classify-food-images-in-different-food-categories-using-yolo11-model-)
2. [Project Overview](#project-overview)
3. [Ultralytics YOLO11](#ultralytics-yolo11)
4. [Modes at a Glance](#modes-at-a-glance)
5. [Dataset](#dataset)
    - [Dataset Splits & Categories](#there-are-3-splits-in-this-dataset)
6. [Directory Hierarchy](#directory-hierarchy)
7. [Requirements](#requirements)
8. [Setup & Getting Started](#lets-start)
    - [1. Create Project Folder](#lets-start)
    - [2. Download Dataset](#lets-start)
    - [3. Prepare Dataset](#lets-start)
    - [4. Setup Virtual Environment](#lets-start)
    - [5. Install Dependencies](#lets-start)
    - [6. Download Pretrained Model](#lets-start)
    - [7. Run Jupyter Notebook](#lets-start)
    - [8. Training & Inference](#lets-start)
9. [Results & Output](#output-in-runs-folder)
10. [Sample Classified Output Images](#classified-output-images)
11. [Troubleshooting](#troubleshooting)
12. [References](#references)
13. [Acknowledgment](#acknowledgment)


## Project Overview

This project applies YOLOv1 to the task of food classification. YOLOv1 is an object detection algorithm that divides images into a grid and predicts bounding boxes and class probabilities for each region. This implementation is focused on food datasets and aims to classify and locate food items in images efficiently.

### Clone the Repository

```bash
git clone https://github.com/vyasdeepti/Food-Classification-using-YOLO11.git
cd Food-Classification-using-YOLO11
```

## Ultralytics YOLO11
[Reference](https://docs.ultralytics.com/models/yolo11/)

Ultralytics YOLO11 is the the latest version of the acclaimed real-time object detection and image segmentation model. YOLO11 is built on cutting-edge advancements in deep learning and computer vision, offering unparalleled performance in terms of speed and accuracy. Its streamlined design makes it suitable for various applications and easily adaptable to different hardware platforms, from edge devices to cloud APIs.

![image](https://github.com/user-attachments/assets/3d1e8650-3e49-49e6-bd3c-35c87b006bbd)

[Image source](https://docs.ultralytics.com/models/yolo11/)

## Modes at a Glance 

Understanding the different modes that Ultralytics YOLO11 supports is critical to getting the most out of your models:

🔶 **Train mode**: Fine-tune your model on custom or preloaded datasets.
Train mode is used for training a YOLO11 model on a custom dataset. In this mode, the model is trained using the specified dataset and hyperparameters. The training process involves optimizing the model's parameters so that it can accurately predict the classes and locations of objects in an image. Training is essential for creating models that can recognize specific objects relevant to your application.

🔶 **Val mode**: A post-training checkpoint to validate model performance.
Val mode is used for validating a YOLO11 model after it has been trained. In this mode, the model is evaluated on a validation set to measure its accuracy and generalization performance. Validation helps identify potential issues like overfitting and provides metrics such as mean Average Precision (mAP) to quantify model performance. This mode is crucial for tuning hyperparameters and improving overall model effectiveness.

🔶 **Predict mode**: Unleash the predictive power of your model on real-world data.
Predict mode is used for making predictions using a trained YOLO11 model on new images or videos. In this mode, the model is loaded from a checkpoint file, and the user can provide images or videos to perform inference. The model identifies and localizes objects in the input media, making it ready for real-world applications. Predict mode is the gateway to applying your trained model to solve practical problems.

🔶 **Export mode**: Make your model deployment-ready in various formats.
Export mode is used for converting a YOLO11 model to formats suitable for deployment across different platforms and devices. This mode transforms your PyTorch model into optimized formats like ONNX, TensorRT, or CoreML, enabling deployment in production environments. Exporting is essential for integrating your model with various software applications or hardware devices, often resulting in significant performance improvements.

🔶 **Track mode**: Extend your object detection model into real-time tracking applications.
Track mode extends YOLO11's object detection capabilities to track objects across video frames or live streams. This mode is particularly valuable for applications requiring persistent object identification, such as surveillance systems or self-driving cars. Track mode implements sophisticated algorithms like ByteTrack to maintain object identity across frames, even when objects temporarily disappear from view.

🔶 **Benchmark mode**: Analyze the speed and accuracy of your model in diverse deployment environments.
Benchmark mode profiles the speed and accuracy of various export formats for YOLO11. This mode provides comprehensive metrics on model size, accuracy (mAP50-95 for detection tasks or accuracy_top5 for classification), and inference time across different formats like ONNX, OpenVINO, and TensorRT. Benchmarking helps you select the optimal export format based on your specific requirements for speed and accuracy in your deployment environment.

![image](https://github.com/user-attachments/assets/4146e3e1-8bf9-49b1-992d-47f4f01b62d5)

[Image source](https://www.researchgate.net/figure/Schematic-representation-of-YOLO11-architecture-This-illustration-highlights-the-key_fig1_388422888)
 
# DATASET
[Dataset link](https://www.kaggle.com/datasets/trolukovich/food11-image-dataset)
Size: 1.19 GB

This dataset contains 16643 food images grouped in 11 major food categories.

## There are 3 splits in this dataset:
```bash
├──Evaluation
├──Training
├──Validation 

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
```

# Directory Hierarchy

```bash
├── YOLO-FOOD-CLASSIFICATION FOLDER
    ├── custom_dataset
          ├── **train** (All 11 classes)
          ├── **val** (All 11 classes)   * We have not considered Evaluation from the dataset
          ├── train.cache (created at runtime)
          ├── val.cache (created at runtime)
    ├── test_images (dataset of images to test)
    ├── PythonCode (jupyter notebook)
    ├── yolo11m-cls.pt/yolo11n.pt... (download the YOLO version)
    ├── myenv (virtual environment)
    ├── .ipynb_checkpoints (created at runtime)
    ├── runs (Output folder)
          ├── classify
                    ├── predict
                    ├── train
          
```
## Requirements

- Python 3.7+
- CUDA-enabled GPU (recommended for training)
- PyTorch
- OpenCV
- NumPy
- Matplotlib
- (Other dependencies as required in `requirements.txt`)


# Let's Start
1. Create a folder "YOLO-FOOD-CLASSIFICATION" (in my case it is in D drive)
2. Download the dataset [Dataset link](https://www.kaggle.com/datasets/trolukovich/food11-image-dataset)
3. Create a folder "custom_dataset" in YOLO-FOOD-CLASSIFICATION folder.
4. Copy training and validation folder from the downloaded dataset into "custom_dataset" folder. I have renamed training folder as "train" and validation folder as "val".
5. For the easy execution, I have not copied / considered evaluation folder from the dataset. So I have only two image folders in custom_dataset.
6. Create a new folder "test_images" in YOLO-FOOD-CLASSIFICATION. Copy 2 to 3 images of each class to be tested. I have searched the images from browser.
7. Open Command prompt (cmd) and navigate to the folder "YOLO-FOOD-CLASSIFICATION".
8. Make sure that python is installed.
9. Create and activate Virtual environment (myenv): 

       Step 1: --Installing virtualenv through pip--
               pip install virtualenv
   
       Step-2: --Creating a virtualenv--
               python -m virtualenv myenv
     
       Step-3: -- Activate the virtual environment--
               myenv\Scripts\activate
   
11. Now you will find a new folder "myenv" created in YOLO-FOOD-CLASSIFICATION folder.
12. In this tutorial we are using "yolo11s-cls.pt" pretrained model of YOLO, which is used for classification. You can download any version of YOLO classification model version from the [link](https://github.com/ultralytics/ultralytics).
13. Keep this downloaded file in YOLO-FOOD-CLASSIFICATION folder.
14. To install jupyter notebook type the command--
    
        pip install jupyter notebook
15. After installation, you can launch Jupyter Notebook with the command--

        jupyter notebook
16. Once jupyter notebook is launched you can see all the folder of YOLO-FOOD-CLASSIFICATION.
17. Create a new file (in my case it is PythonCode) and execute the cells

        pip install ultralytics  
        pip install --upgrade pip

        from ultralytics import YOLO
        createdmodel=YOLO("yolo11s-cls.pt")
        results= createdmodel.train(data="custom_dataset",epochs=8,imgsz=640 )

        #USING PRETRAINED MODEL
        model_test=YOLO("runs/classify/train/weights/best.pt")
        results=model_test("test_images", save=True, imgsz=320, conf=0.7)
        results[0].show()

    
19. A new folder "runs" will be created. As we have a large dataset to process, it will take a good amount of time to get executed. 

        runs --> classify --> predict and train
    
21. In the predict folder you will get the output of the images which we have given to test from "test_images" folder.
22. In the train folder we will get weights (best.pt and last.pt), args, results, confusion matrixand other inferenced information.

# Output (in runs folder)

Read more about 
- [Confusion Matrix](https://www.datacamp.com/tutorial/what-is-a-confusion-matrix-in-machine-learning) 
- [Epochs, Iteration and batch](https://medium.com/@akankshaverma136/epochs-batch-and-iterations-in-deep-learning-ed319565e85e)
- [Yolo11 Architecture](https://www.researchgate.net/figure/Schematic-representation-of-YOLO11-architecture-This-illustration-highlights-the-key_fig1_388422888)

![confusion_matrix_normalized](https://github.com/user-attachments/assets/e2cfb7f5-8555-49e7-bac2-6fbe8927f0c5)
![results](https://github.com/user-attachments/assets/d07d8924-375e-4120-aabc-5a4874b198aa)
![confusion_matrix](https://github.com/user-attachments/assets/cfaff543-db7f-4087-8b8f-9403f41ea3c9)

```
epoch	time	train/loss	metrics/accuracy_top1	metrics/accuracy_top5	val/loss	lr/pg0	lr/pg1	lr/pg2
1	1282.13	1.12327	0.85627	0.9895	0.45432	0.000221973	0.000221973	0.000221973
2	2637.63	0.61349	0.85773	0.9898	0.47545	0.000389323	0.000389323	0.000389323
3	3932.97	0.55246	0.86706	0.9898	0.4217	0.000501646	0.000501646	0.000501646
4	5334.54	0.46953	0.88105	0.99446	0.38488	0.000419376	0.000419376	0.000419376
5	6743.64	0.39123	0.89563	0.99359	0.33717	0.000336835	0.000336835	0.000336835
6	8026.88	0.31035	0.90554	0.99475	0.30944	0.000254294	0.000254294	0.000254294
7	9172.25	0.23643	0.92012	0.99679	0.26922	0.000171752	0.000171752	0.000171752
8	10363.8	0.18238	0.92449	0.99679	0.23753	8.92E-05	8.92E-05	8.92E-05

```


![image](https://github.com/user-attachments/assets/bc3da640-1252-4c1c-9bfc-f051eb87f18c)


# Classified output images:

![0](https://github.com/user-attachments/assets/f3278888-1729-414c-a67f-3ebacd48aa8d)
![10](https://github.com/user-attachments/assets/228fbdaf-39c7-4f18-8b5f-c5437d1ee3b2)
![11](https://github.com/user-attachments/assets/529a5718-fe09-4b59-ba18-d68a0d447bfe)
![4](https://github.com/user-attachments/assets/857cbfdd-044b-424f-88a7-f94273428b8e)


## Troubleshooting

- **CUDA Out of Memory:** Reduce batch size or image size.
- **Incorrect Dataset Format:** Ensure annotations are in YOLO format and the directory structure matches expectations.
- **Missing Dependencies:** Install all required packages.


## References

- [YOLOv1 Paper](https://arxiv.org/abs/1506.02640)
- [PyTorch YOLO Implementations](https://github.com/eriklindernoren/PyTorch-YOLOv3)
- [Food-101 Dataset](https://data.vision.ee.ethz.ch/cvl/datasets_extra/food-101/)


## Acknowledgment
- This package is powered by [ultralytics YOLO](https://github.com/ultralytics/ultralytics) for object detection.
- Special thanks to the open-source community for their contributions.



              
         
   
