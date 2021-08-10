# ECG Arrythmia Detection

ECG is a biosignal that provides insight on heart's electrical activity and it's rythm. Detecting Arrythmia from ECG signals require medical expertise which is not accessible to all. A machine learning model paired with a ECG Holter can help address this issue.

This project utilizes MIT-BIH dataset to train different machine learning models (LR, SVM and CNN) and find the optimum model for arrythmia detection. Based on the R-peak of ECG signal, the models classify the ECG signals into seven categories:
* Normal
* Arrhythmias
  * Left Bundle Branch Block
  * Right Bundle Branch Block
  * Premature Ventricular Contraction
  * Ventricular Escape Rhythm
  * Paced Rhythm
  * Atrial Premature Contraction
## Dataset

The [MIT-BIH Arrhythmia Dataset ](https://physionet.org/content/mitdb/1.0.0/)
was the first set of standard test material that was generally available to evaluate arrhythmia detection. ECG signals were described by a text header file (.hea), a binary file (.dat) and a binary annotation file (.atr). The source of the ECGs included in the MIT-BIH Arrhythmia Database is a set of over 4000 long-term Holter recordings. In most records, the upper signal is a modified limb lead II (MLII), obtained by placing the electrodes on the chest. 

  
## Progress

- ~~Data Extraction~~
- ~~R-Peak Detection~~
- ~~ECG Signal Segmentation~~
- ~~Resample~~
- ~~Standardize~~
- ~~Train Model (LR, SVM, 1D-CNN)~~
- ~~Test Model (Precision, Recall, Accuracy, Loss, Confusion Matrix)~~
- ~~Web Deployment~~



## CNN Architecture

![alt cnn](/saved_figures/cnn.png)

## Model performance of CNN

|  | Paced | APC | VEB | LBB | Normal | RBB | PVC | Total
| :---         |     :---:      |          :---: | :---:        |     :---:      |          :---: |  :---:        |     :---:      |          :---: |
|Training data| 16200 | 16200 | 16200 | 16200 | 16200 | 16200 | 16200 | 113400
| Validation data | 1800 | 1800 | 1800 | 1800 | 1800 | 1800 | 1800 |12600
|Correct Prediction | 16194 | 16170 | 16200 | 16189 | 16140 | 16191 | 16165 | 113249
|Sensitivity | 99.9% | 99.8% | 100% | 99.9% | 99.6% | 99.9% |99.7% | 99.8%

  
## Training and validation gain/loss of the CNN model

*The training performance gradually improved after each iteration and remained stable. After 25 iterations or epochs, an averaged accuracy of 99.8% was achieved in the validation set for the arrhythmia classification. The loss also reduced after each iterations and an average loss of 0.5% was achieved.*
<br />

<p float="left">
  <img src="/saved_figures/train-val.png" />
  <img src="/saved_figures/train-val%20accuracy.png" /> 
  
</p>

## Tech Stack

* DSP (bioSPPy)
* sklearn
* Matplotlib
* Pandas
* Numpy
* wfdb
* Keras/ tensorflow

