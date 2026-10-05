# CodeAlpha_HandwrittenRecognition

Handwritten digit recognition with a Convolutional Neural Network (CNN),
built during my Machine Learning internship at CodeAlpha.

## Objective
Identify handwritten digits (0-9) from images using image processing and deep learning.

## Dataset
MNIST: 60,000 training and 10,000 test images (28x28 grayscale).

## Approach
1. Scaled pixel values to 0-1 and added a channel dimension
2. Built a CNN: 2 convolution + max-pooling blocks, Flatten, Dropout (0.3), Dense (softmax)
3. Trained for 8 epochs (batch size 128, 10% validation split) with the Adam optimizer
4. Evaluated with accuracy, precision, recall, F1-score and a confusion matrix
5. Added a prediction function that preprocesses my own drawings the same way MNIST digits are prepared (crop, resize to 20x20, center on 28x28)

## Results
- **Test accuracy: 98.84%** (116 mistakes out of 10,000 images)
- Weakest digit: 9 (recall 0.976)
- Most common confusion: 5 predicted as 3 (8 times)
- Many mistakes were unclear or ambiguous handwriting

## Lesson learned
My own thin Paint drawing was first misread. After preprocessing it like MNIST,
the model predicted it correctly. New data must be prepared like training data.

## How to run
pip install -r requirements.txt
Open digit_recognition.ipynb and run all cells.

## Files
- digit_recognition.ipynb: full code and results
- digit_cnn.keras: trained model
- my_digit.png: sample drawing for testing