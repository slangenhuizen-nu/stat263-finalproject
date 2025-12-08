# stat263-finalproject
__Project:__ Breast Cancer Imaging Classification

__Course:__ STAT 362-0

__Quarter:__ Fall 2025

__Team Members:__ Sofie Langenhuizen, Gabriella Messenger, Leah Tan

Breast cancer remains a leading cause of death for women worldwide, accounting for 24.2% of cancer cases in women _(Barrios 2022)_. Early detection of tumors at a localized stage is the most effective combative strategy to improve outcomes, increasing the relative 5-year relative survival rate to 99% _(Shockney 2023)_. We aim to leverage deep learning models to enhance these early detection models. Unlike traditional diagnostic methods like MRIs, which are costly and extremely limited in predictive capability due to the complexity of interpretation, models like convolutional neural networks (CNNs) offer a more accessible and efficient process. These models can identify subtle anomalies more quickly, and in many cases, more accurately. Thus, CNNs can not only improve the quality of medical images, but also serve as powerful predictive tools in early-stage diagnosis _(Khalid 2023)_.

__Model:__ 
Baseline keras CNN with 5 convolutional layers, 2 dense layers with ‘relu’ activation and ‘softmax’ output. It is regularized with dropout set to 40% and a defined early stopping function. It is optimized with respect to default Adamax configuration. It is trained on a batch size of 32 and 50 epochs.  

__Summary of key results:__

Our final model achieved a training accuracy of 75.00% and a test accuracy of 79.01%.  
A summary of the different models we experimented with is provided below:

| **Model**             | **Summary**                                                                                                                                                                               | **Training Accuracy** | **Test Accuracy** |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- | ----------------- |
| **Initial Model**     | - 4 convolutional blocks<br> - 1 fully connected layer<br> - Softmax output layer                                                                                                         | **70.04%**            | **69.14%**        |
| **ResNet Model**      | - ResNet-50 architecture<br> - GlobalAveragePooling layer<br> - Dropout layer<br> - Softmax output layer                                                                                  | **59.38%**            | **59.26%**        |
| **Focal Loss Model**¹ | - 5 convolutional blocks<br> - 3 dense layers<br> - Softmax output layer<br> - Dropout layer<br> - Focal loss function                                                                    | **65.62%**            | **74.39%**        |
| **Keras Tuner Model** | - Same architecture as initial model<br> - Added dropout layer<br> - Tuned hyperparameters (activation function, dense units, filters, padding, kernel size, dropout rate, learning rate) | **74.26%**            | **77.78%**        |
| **Final Model**       | - 4 convolutional blocks<br> - 2 fully connected layers (each followed by a dropout layer, dropout = 0.4)<br> - Softmax output layer                                                      | **75.00%**            | **79.01%**        |

---



**Training and validation accuracy and loss plots:** 


<img width="821" height="302" alt="Screenshot 2025-12-06 at 4 20 49 PM" src="https://github.com/user-attachments/assets/699c580a-4df7-4198-966f-bcb9aaf90e63" />


---

__Confusion matrices:__


**Training**
|       |              |              | **Predicted** |              |
|--------------|---------------|------------|----------------|------------|
|              |              | **benign** | **malignant** | **normal** |
|| **benign**    | 194        | 62             | 49         |
| **True**     | **malignant** | 96         | 24             | 27         |
|              | **normal**    | 59         | 16             | 17         |

---

**Validation**
|              |              |              | **Predicted** |              |
|--------------|---------------|------------|----------------|------------|
|              |              | **benign** | **malignant** | **normal** |
|| **benign**    | 60        | 12             | 15         |
| **True**     | **malignant** | 19         | 9             | 14         |
|              | **normal**    | 15         | 6             | 5         |


---
**Test**
|             |              |              | **Predicted** |              |
|--------------|---------------|------------|----------------|------------|
|              |              | **benign** | **malignant** | **normal** |
|| **benign**    | 26        | 9             | 10         |
| **True**     | **malignant** | 13         | 4             | 4         |
|              | **normal**    | 8         | 4             | 3         |

---



__Steps to run the code:__

1. Create a virtual environment with the following command in your terminal.
```bash
python -m venv venv
```

2. Open a new terminal. 
Install dependencies with the following command in your terminal. 
```bash
pip install -r requirements.txt
```

3. Run `scripts/data_processing.ipynb` notebook to create new file directories and split data.

4. Run `scripts/final_model.ipynb` notebook to create and run the classification model and see output results. 



