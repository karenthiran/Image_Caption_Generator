Overview
Image captioning involves using deep learning models, like CNNs for feature extraction and LSTMs for sequence generation, to create descriptive text for images. Leveraging frameworks like TensorFlow and Keras, models can be trained to interpret and describe visual content. This technology is used in various applications, from accessibility tools to social media platforms.

![image](https://github.com/karenthiran/Image_Caption_Generator/blob/a63168266ae85c167d1020df30d7765003be3634/image.png)

EC9170 - Deep Learning for Electrical & Computer Engineers 
Mini Project
Building an Image Caption Generator using CNN-LSTM from Scratch

Data Preprocessing Methodology
In this project, we utilized the given dataset for image captioning. The preprocessing pipeline involved several crucial steps to prepare both the images and the textual descriptions for model training.
1. Image Preprocessing
  • Feature Extraction: Pre-trained CNN (InceptionV3) was used to extract visual features from images.
  •	Image Resizing: All images were resized to the shape required by InceptionV3 (299x299x3).
  •	Normalization: Pixel values were scaled to the range [0, 1] as expected by the model.
2. Text Preprocessing
  •	Cleaning Captions:
    •	Converted all captions to lowercase.
    •	Removed punctuation, digits, and special characters using regex.
    •	Removed short or meaningless words (e.g., single characters).
  •	Tokenization:
    •	Added special tokens: 'startseq' at the beginning and 'endseq' at the end of every caption.
    •	Tokenized captions using Keras’ Tokenizer and converted them to integer sequences.
    •	Vocabulary Construction:
    •	Built a vocabulary from all unique words across the training captions.
    •	Calculated the vocabulary size, which was used during training.
3. Data Generator Creation
  •	A custom data generator was implemented to:
    •	Feed input data in batches.
    •	Avoid memory overload by not loading the entire dataset into memory.
    •	Yield tuples of input image features, input sequences, and output words (one word at a time).


