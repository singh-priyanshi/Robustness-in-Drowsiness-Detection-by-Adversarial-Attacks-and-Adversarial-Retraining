# Comparative study of Robustness in Drowsiness Detection by Adversarial Attacks and Adversarial Retraining
Final Project for the course ECE-9133- Machine Learning For Cybersecurity  

## Project Overview

This repository contains the code and documentation for the final project titled "Comparative Study of Robustness in Drowsiness Detection by Adversarial Attacks and Adversarial Retraining," presented by Moin Khan (mk8793), Ishan Miglani (im2410), Priyanshi Singh (ps4609), and Siddharth Singh (ss16915) for the course EL-GY-9163: Machine Learning for Cyber-security.

## Project Presentation

The project presentation slides, video, and report are available in the "Presentation" folder. The presentation covers the project's needs, approach, adversarial attack techniques, benefits, competition with Mobilenet V2 and Custom CNN models, deliverables, references, and team member contributions.

## Saved Models

The retrained models against each attack for both the Mobilenet V2 and the Custom CNN architectures are available at: [Drive Link](https://drive.google.com/drive/folders/14i9ji9RnqabFeQWVTxtcFQmQHO2TvmED?usp=sharing)

## Code Structure

For each model, MobileNet V2 and Custom CNN, there are two specific Python notebooks. Each notebook contains code for training the model on clean data. Additionally, each model notebook performs multiple adversarial attacks on the model, including "FGSM," "PGD," "Auto-PGD," "DDN," "DeepFool," "Patch," "Carlini Wagner," and "Boundary Attack."

### Code Usage

1. Each attack includes two functions: one for generating adversarial data and the other for retraining the model to enhance its robustness against adversarial attacks.
2. For example, in the case of the FGSM attack:
   - `fgsm_attack_with_generator` is used to generate adversarial images.
   - `retrain_model_with_fgsm` is used to retrain the model on adversarial data.

3. The code also compares the accuracy of the model on adversarial data before and after the model retraining.

### Dataset
Datasets: In this study, we leveraged the Closed Eyes in the Wild (CEW) dataset, a comprehensive collection comprising 1452 subjects. Within this dataset, 726 individuals exhibit closed eyes, while 726 individuals have open eyes. The CEW dataset provides a diverse set of scenarios, enriching our understanding of drowsiness detection. Our focus on the CEW dataset ensures a robust exploration of drowsiness detection across varied subjects and conditions. Figure 1 illustrates examples from the CEW dataset. 
![image](https://github.com/singh-priyanshi/ML-for-Cybersec-Final-Project/assets/31034647/1e0e6fa2-f1a6-468d-ac9d-05b7d1ee07d0)
<br>Figure 1: Sample Images from CEW DataSet

## Adversarial Attacks and Results

### 1. Fast Gradient Sign Method (FGSM) Attack

- Perturbation Strength (ϵ): 0.01
- Retraining Samples: 25%
- Results:
  - Model 1 (Mobilenet V2) Accuracy (Before / After Retraining): 0.84 / 0.514
  - Model 2 (Custom CNN) Accuracy (Before / After Retraining): 0.945 / 0.962

### 2. Projected Gradient Descent (PGD) Attack

- Perturbation Strength (ϵ): 0.01
- Retraining Samples: 25%
- Results:
  - Model 1 (Mobilenet V2) Accuracy (Before / After Retraining): 0.78 / 0.997
  - Model 2 (Custom CNN) Accuracy (Before / After Retraining): 0.922 / 0.942

### 3. Auto Projected Gradient Descent (Auto-PGD) Attack

- Perturbation Strength (ϵ): 0.01
- Retraining Samples: 25%
- Results:
  - Model 1 (Mobilenet V2) Accuracy (Before / After Retraining): 0.68 / 1.0
  - Model 2 (Custom CNN) Accuracy (Before / After Retraining): 0.94 / 0.97

### 4. Decoupling Direction and Norm (DDN) Attack

- Perturbation Strength (ϵ): 0.01
- Number of Steps: 40
- Results:
  - Model 1 (Mobilenet V2) Accuracy (Before / After Retraining): 0.824 / 0.9979
  - Model 2 (Custom CNN) Accuracy (Before / After Retraining): 0.914 / 0.97

### 5. DeepFool Attack

- Max Iterations: 100
- Logits models (instead of softmax probability model)
- Results:
  - Model 1 (Mobilenet V2) Accuracy (Before / After Retraining): 0.435 / 0.91
  - Model 2 (Custom CNN) Accuracy (Before / After Retraining): 0.019 / 0.965

### 6. Patch Attack

- Images Considered for Patch: 100
- Batch Size: 64
- Learning Rate: 5000.
- Max Iterations: 100
- Results:
  - Model 1 (Mobilenet V2) Accuracy (Before / After Retraining): 0.54 / 0.91
  - Model 2 (Custom CNN) Accuracy (Before / After Retraining): 0.4 / 0.977

### 7. Carlini Wagner

- Batch Size: 32
- Learning Rate: 0.01
- Distance Metric: L2
- Max Iterations: 100
- Results:
  - Model 1 (Mobilenet V2) Accuracy (Before / After Retraining): 0.51 / 0.99
  - Model 2 (Custom CNN) Accuracy (Before / After Retraining): 0.89 / 0.98

### 8. Boundary Attack

- Batch Size: 32
- Epsilon: 0.01
- Max Iterations: 100
- Results:
  - Model 1 (Mobilenet V2) Accuracy (Before / After Retraining): 0.07 / 1.0
  - Model 2 (Custom CNN) Accuracy (Before / After Retraining): 0.05 / 0.90

## Benefits and Competition

### Benefits

1. **Enhanced Safety:** Reduces accident risks with more reliable detection.
2. **Greater Accuracy:** Improves model performance in identifying drowsiness.
3. **Increased Resilience:** Strengthens defenses against adversarial attacks.
4. **Broader Research Contributions:** Offers insights for AI security and robustness.
5. **Wider Sector Application:** Useful across automotive, industrial, and healthcare sectors.

### Competition (Mobilenet V2 vs. Custom CNN)

| Parameters        | Mobilenet V2 | Custom CNN |
|-------------------|--------------|------------|
| Number of Parameters | 3,360,322 | 5,561,922 |
| Accuracy | 1.0 | 1.0 |
| FGSM Attack Accuracy | 0.514 | 0.962 |
| PGD Attack Accuracy | 0.997 | 0.942 |
| Auto-PGD Attack Accuracy | 1.0 | 0.97 |
| DDN Attack Accuracy | 0.9979 | 0.97 |
| DeepFool Attack Accuracy | 0.91 | 0.965 |
| Patch Attack Accuracy | 0.91 | 0.977 |
| Carlini Wagner Attack Accuracy | 0.99 | 0.98 |
| Boundary Attack Accuracy | 1.0 | 0.90 |

**\*** Accuracy is calculated after retraining for each attack

## Results

![image](https://github.com/singh-priyanshi/ML-for-Cybersec-Final-Project/assets/31034647/eaf8837c-2f43-4bd2-9f70-9bd53ee72ca7)
<br>Figure 2: Accuracy comparison of models before re-training on adversarial data

![image](https://github.com/singh-priyanshi/ML-for-Cybersec-Final-Project/assets/31034647/09d28460-64f7-46e3-b0f1-36a21a9785eb)
<br>Figure 3: Accuracy comparison of models after re-training on adversarial data

## References

- Gwak, J., Hirao, A., Shino, M. (2020). [An investigation of early detection of driver drowsiness using ensemble machine learning based on hybrid sensing.](https://www.mdpi.com/2076-3417/10/8/2890)
- Mehta, S., Dadhich, S., Gumber, S., Bhatt, A.J. (2019). [Real-time driver drowsiness detection system using eye aspect ratio and eye closure ratio.](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3356401)
- Closed Eye in the Wild dataset (CEW): [CEW Databases](http://parnec.nuaa.edu.cn/_upload/tpl/02/db/731/template731/pages/xtan/ClosedEyeDatabases.html)
- Adversarial Robustness Toolbox: [ART Documentation](https://adversarial-robustness-toolbox.readthedocs.io/en/latest/)

## Acknowledgments

Special thanks to our instructors and teaching assistants, Marco Romanelli, Alexandre Araujo, Naman Patel, Chinmay Nerurkar, Chandana Srinivasa, Mahmoud Shabana, and Mingzhi Zhu, for their guidance, expertise, and unwavering commitment throughout the course (EL-GY-9163: Machine Learning for Cyber-security). Your contributions have been invaluable to our learning experience.

Thank you for making this course an enriching and impactful journey!
