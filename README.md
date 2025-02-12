# CV--Plants-Seedling-Classification
A robust image classifier using CNNs to efficiently classify different plant seedlings and weeds to improve crop yields and minimize the extensive human effort to do this manually.

The model used in this project is a Sequential CNN Model. This model is a type of convolutional neural network designed to process data in a sequential order, meaning it analyzes data one element at a time, like a sequence of images in a video or words in a sentence, by stacking convolutional layers with other layers like recurrent neural networks (RNNs) to capture temporal dependencies within the data, making it particularly useful for tasks like video classification or natural language processing where order matters. 

![seedlings_preprocessing](https://github.com/user-attachments/assets/d176fa2f-a8ae-4ada-8c9c-1ca2fff6eb62)

The strategy included analyzing the 128 x 128 pixels images to determine if there was too much data loss when converted or reduced down to 64 x 64 pixels. This pixel dowscaling reduces the filter size, convolutional processing thus improving the performance of the neural network model.

![seedlings_preprocessing_2](https://github.com/user-attachments/assets/5e7cac11-1991-4928-b62a-02b2d63d2ec8)

The file containg the images was too large to include it in GitHub at 200+ MBs. Only the Labels file was included.

Train-Test-Validate dtaset splits were as follows:

    Shape of training dataset:
    (3800, 64, 64, 3) (3800, 1)

    Shape of validation dataset:
    (475, 64, 64, 3) (475, 1)

    Shape of testing dataset:
    (475, 64, 64, 3) (475, 1)

The attributes of the Sequential CNN model was as follows:

![Sequential CNN Model](https://github.com/user-attachments/assets/9ddd9fb3-bb2f-41de-9d19-b1917e488bef)

The Architecture of the Model:

![Sequential CNN Model 2](https://github.com/user-attachments/assets/59040064-52e1-4126-81d5-1c5f3177ab1a)

After Training the Test and Validation datasets accuracy was measured and it indicated the model was Overfitting.
Notice the Training accurcy is significantly higher than the validation accuracy, meaning the model performs very well on the training data but poorly on the validation data.

![model evaluations](https://github.com/user-attachments/assets/543390bf-a715-4222-aae2-7259988e0256)

Strategies to balance datasets to prevent Overfitting/Underfitting - Courtesy of IBM: 

**Decrease regularization**

Regularization is typically used to reduce the variance with a model by applying a penalty to the input parameters with the larger coefficients. There are a number of different methods, such as L1 regularization, Lasso regularization, dropout, etc., which help to reduce the noise and outliers within a model. However, if the data features become too uniform, the model is unable to identify the dominant trend, leading to underfitting. By decreasing the amount of regularization, more complexity and variation is introduced into the model, allowing for successful training of the model.

**Increase the duration of training**

As mentioned earlier, stopping training too soon can also result in underfit model. Therefore, by extending the duration of training, it can be avoided. However, it is important to cognizant of overtraining, and subsequently, overfitting. Finding the balance between the two scenarios will be key.

**Feature selection**

With any model, specific features are used to determine a given outcome. If there are not enough predictive features present, then more features or features with greater importance, should be introduced. For example, in a neural network, you might add more hidden neurons or in a random forest, you may add more trees. This process will inject more complexity into the model, yielding better training results.

![Normalization](https://github.com/user-attachments/assets/f135accf-75ee-4024-8e52-4933a763fd34)

Now, after Normalization and Data Augmentation:

![Normalization - 2](https://github.com/user-attachments/assets/a2540d8a-60ab-4044-ba00-02864e82bac2)

Now we will use the VGG16 Model keeping in mind the following advantages: 
-  Uses only 3x3 convolutions and 2x2 max pooling throughout
  
-  ReLU activation functions after each convolutional layer
  
-  Final softmax layer for classification
  
-  Often used as a feature extractor for computer vision tasks
  
-  It is computational intensive and uses a lot of memmory

![VGG16 Model](https://github.com/user-attachments/assets/3019f53e-d618-41a1-8fd8-507be25cc80b)

Notable results: 

![VGG16 Model 2](https://github.com/user-attachments/assets/5e867940-d15f-409b-865c-8d66c8f487ca)

There were multiple tradeoffs observed after fine tuning the models and even using different models, such as some models exhibited faster results, but overfitting and dignigficant processing time.

Conclusions:

![Conclusions](https://github.com/user-attachments/assets/a4195e67-55a6-4fbc-93a5-ad727f33d810)

  
