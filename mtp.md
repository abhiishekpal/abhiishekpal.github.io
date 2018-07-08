---
layout: page
title: MTP
permalink: /mtp/
---
# EEG signal Based Image Classification.
	
My Major Technical Project for the Bachelor Degree.

Mentors:
- Dr. Arnav Bavsar
- Dr. Varun Dutt	

## Paper 1: Personalized Image classification from EEG signal

- The paper proposes a end to end deep learning based model for classification of 40 classes from ImageNet dataset.
- Main contribution of the paper here is to adapt this developed universal model to new user(i.e user specific model).


Model Used: **LSTM**	 (Long short term memory)\\
LSTM are improved version of traditional RNN model with gating mechanism which helps to greatly reduce the prolem of vanishing and exploding gradients.

![LSTM model](https://image.ibb.co/kFYMj8/Screenshot_from_2018_07_08_20_37_33.png)

Great sources to study about LSTM:
- [Lecture by Richard Socher](https://youtu.be/QuELiw8tbx8).
- [Lecture by Ali Ghodi](https://youtu.be/EAt9_4IhC7s).

# Architecture
- Two stacked LSTM.
- A dense layer at the end of LSTM.
- Followed by a softmax classification layer.

![Architecture of model](https://image.ibb.co/mgwVcT/Screenshot_from_2018_07_08_20_37_13.png)

# Dataset
- EEG singnals of 5 subjects, 40 classes of Imagenet with each class having 50 sample Image.
- Show time: 0.5 sec.
- Train on 80%, Validataion on 10% and Test on 10%.

- The input to the network is the EEG signal.
- EEG signals are recorded on a 10-20 electrode using 128 channel brain cap.
- the signals are capture for 500 ms hence the data to be input present is of dimension 128 X 500.
- But to avoid any noise due to overlap the signals captured from 250-450ms duration are fed into the network. Input dimension: 128 X 200



# Personalized model
Once the model has been trained for universal data. The paper tries to tune the performance acording to user.
- Transfer Learning was used to accomplish this task.
- The dense layer and the classification layer were re trained with the fixed LSTM weights.
- This model gave significant improvement on user specific data for a person.

![Personalized Model](https://image.ibb.co/gvfZ48/Screenshot_from_2018_07_08_20_37_22.png)







