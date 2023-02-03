<img width="701" alt="image" src="https://user-images.githubusercontent.com/110128293/216616741-ae344560-435a-427a-ae9f-85bfdf8249ab.png">

# Qar'i - Classifying Arabic Handwritten Characters

## Elevator Pitch
Arabic is a critical need language, meaning linguists are in short supply for the amount of work available. Qar'i's AI/ML model is intended to be incorporated into applications where the identified characters are output into files for use with machine translation services, thus reducing the burden on linguists.


## What is it?
Qar'i is a proof-of-concept, machine-learning solution designed to recognize hand-written Arabic characters.

## Who is the intended stakeholder? 
The intended stakeholder is a defense, security, or justice (DS&J) professional who is not able to read Arabic or one who needs to triage a large set of documents in a short amount of time; however, this proof-of-concept could be extended to any professional who cannot read Arabic or is not able to read Arabic proficiently. 

## Why would this solution be used?
I propose two use cases for this project. 

First, this solution would be used to augment a business unit who is unable to staff sufficient numbers of Arabic linguists; in such an instance, this tool would ideally enable a team to identify documents that have suspicious or derogatory information. A team would then be able to refer these documents to trained linguists as a priority for translation.

Second, a unit that has trained linguists may receive a sufficiently-high volume of handwritten documents that they are unable to translate the documents in an time-efficient manner or without undue fatigue. In this sense, it is important that have some means of prioritizing which documents to complete a full translation on versus which to delay.

Regardless, the purpose of this project is to save a team seconds or minutes in a field where time is often of the essence.

## How is this solution's machine-learning model generated?
This solution utilizes convolutional neural networks as an image classification algorithm meaning that, with initially labeled training data, the algorithm allows the computer to adapt the filters by itself to achieve a result.

## Model
The model being created is a convolutional neural network that should essentially mimic an animal's acquisition of data about their surroundings by sight, or the human ability to read. A callback has been included so that the model is interrupted when validation loss begins to increase, so as to limit the amount of overfitting present in the model.

## Training the Model
This model is trained using the Training dataset that we pulled from the directory. The model performance is then validated using the Validation dataset that was set aside using the dataset_from_directory command.
![image](https://user-images.githubusercontent.com/110128293/216598490-545e52d7-f2f1-40c8-b314-1f284a0566fe.png)
![image](https://user-images.githubusercontent.com/110128293/216598512-dbc7e2ae-5247-45e3-99a8-012901cd0c04.png)
![image](https://user-images.githubusercontent.com/110128293/216598524-b2141d53-137e-4e6c-8e23-d9db115722db.png)
![image](https://user-images.githubusercontent.com/110128293/216598538-14b3a55b-e8c4-4f94-b6e9-42697bddc29f.png)

## Performance Evaluation
Overall, this model has flaws that need to be rectified.
The accuracy of the model leaves much to be desired, and would hinder the analyst more than aid them due to the inability to reliably recognize the 28 Arabic characters. 

While it is good that we have a high recall, where the model is reliably retrieving relevant results, this should be expected as we were conducting supervised learning, where the network was able to refer to the labels during training.

The model's precision suggests that it is relatively unreliable at producing results that are relevant. That is, this model is relatively unable to separate the wheat from the chaff.

Accuracy similarly needs improvement. The model is only performing at 73% accuracy, which is much lower than a DS&J professional would need. In a short 500 word document, the model would be unable to recognize 135 words because it could not accurately interpret the letters in the document.



## Conclusion

At this point in development, we would recommend that this machine-learning model *not* be incorporated into any applications or products. While the model is not currently ready for use, it has succeeded in its role as a proof of concept.

# Repository Navigation
The Jupyter notebook contains the code for the models and the evaluation metrics derived from the model. The images used are in a .ZIP file; the original dataset for this model was slightly modified by making additional folders for each class. 

## References:
Mohamed Loey. 2018. Arabic Handwritten Characters Dataset. Kaggle. URL: https://www.kaggle.com/datasets/mloey1/ahcd1

Peter Mortensen. 2022. Answer to "Error '(unicode error) 'unicodeescape' codec can't decode bytes in position 2-3: truncated \UXXXXXXXX escape'". 
StackOverflow. 16 September. URL: https://stackoverflow.com/questions/37400974/error-unicode-error-unicodeescape-codec-cant-decode-bytes-in-position-2-3

Keras. 2023. Image Data Preprocessing. URL: https://keras.io/api/preprocessing/image/

Geeks for Geeks. 2023. Choose Optimal Number of Epochs to Train a Neural Network in Keras. 10 January. 
URL: https://www.geeksforgeeks.org/choose-optimal-number-of-epochs-to-train-a-neural-network-in-keras/

Santhoopa Jayawardhana. 2020. Sequence Models & Recurrent Neural Networks (RNNs). Towards Data Science. 27 July. 
URL: https://towardsdatascience.com/sequence-models-and-recurrent-neural-networks-rnns-62cadeb4f1e1#:~:text=Sequence%20models%20are%20the%20machine,algorithm%20used%20in%20sequence%20models.

Sanket Doshi. 2019. Various Optimization Algorithms for Network Training Neural Network. Towards Data Science. 13 January. 
URL:https://towardsdatascience.com/optimizers-for-training-neural-network-59450d71caf6#:~:text=Gradient%20Descent%20is%20the%20most,linear%20regression%20and%20classification%20algorithms.
