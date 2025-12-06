# stat263-finalproject
__Project:__ Breast Cancer Imaging Classification
__Course:__ STAT 362-0
__Quarter:__ Fall 2025
__Team Members:__ Sofie Langenhuizen, Gabriella Messenger, Leah Tan

Breast cancer remains a leading cause of death for women worldwide, accounting for 24.2% of cancer cases in women _(Barrios 2022)_. Early detection of tumors at a localized stage is the most effective combative strategy to improve outcomes, increasing the relative 5-year relative survival rate to 99% _(Shockney 2023)_. We aim to leverage deep learning models to enhance these early detection models. Unlike traditional diagnostic methods like MRIs, which are costly and extremely limited in predictive capability due to the complexity of interpretation, models like convolutional neural networks (CNNs) offer a more accessible and efficient process. These models can identify subtle anomalies more quickly, and in many cases, more accurately. Thus, CNNs can not only improve the quality of medical images, but also serve as powerful predictive tools in early-stage diagnosis _(Khalid 2023)_.

__Model:__ 
Baseline keras CNN with 5 convolutional layers, 2 dense layers with ‘relu’ activation and ‘softmax’ output. It is regularized with dropout set to 40% and a defined early stopping function. It is optimized with respect to default Adamax configuration. It is trained on a batch size of 32 and 50 epochs.  

__Summary of key results__
_[[NEED TO UPDATE]] You may reuse plots or metrics from your final presentation slides._

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

3. Run data_processing.ipynb notebook to create new file directories and split data.

4. Run final_model.ipynb notebook to create and run the classification model and see output results. 



