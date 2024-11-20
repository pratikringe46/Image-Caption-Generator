# Image-Caption-Generator

This is an **Image Caption Generator** project that generates descriptive captions for images. The project uses the pre-trained **VGG16 model** for feature extraction and a custom encoder-decoder architecture built with TensorFlow and Keras.

## Features

- Extracts visual features using the **VGG16 model**.
- Processes captions with a **tokenizer** to create a vocabulary and integer mappings.
- Uses a **generator function** to handle large datasets efficiently.
- Employs Long Short-Term Memory (LSTM) networks for caption generation.
- Combines image and caption features in an encoder-decoder model for caption generation.
- Trained on a diverse dataset of 8,000+ images and 40,000 captions.
  

## Dataset: Flickr8k

The **Flickr8k dataset** is widely used for image captioning tasks. It consists of:
- **8,000 images**.
- **5 captions per image**.

The images capture a diverse range of scenes, including sports, animals, urban settings, and everyday life. This dataset is widely used in research to develop and evaluate image captioning models.

## Project Workflow

1. **Feature Extraction**:
   - Resizes images and preprocesses them using the VGG16 preprocessing pipeline.
   - Extracts 4096-dimensional feature vectors for each image.

2. **Caption Processing**:
   - Loads captions and maps each word to unique integer indices using a tokenizer.
   - Splits sequences into input-output pairs for training.

3. **Model Architecture**:
   - **Encoder**: Processes image features with dense and dropout layers.
   - **Decoder**: Combines image and text features using LSTM layers.
   - **Output**: Predicts the next word in the sequence using softmax activation.

4. **Training**:
   - Uses a generator to process data in batches to prevent memory overload.
   - Trains the model using categorical cross-entropy loss and Adam optimizer.

5. **Caption Generation**:
   - Takes an image and generates captions word by word.
   - Stops when an end tag is encountered or the maximum sequence length is reached.

## Results
---------------------Actual---------------------<br>
start black dog and spotted dog are fighting end<br>
start black dog and tri-colored dog playing with each other on the road end<br>
start black dog and white dog with brown spots are staring at each other in the street end<br>
start two dogs of different breeds looking at each other on the road end<br>
start two dogs on pavement moving toward each other end<br>
--------------------Predicted-------------------- <br>
start black and white dog is running through the beach end<br>
![img1](https://github.com/pratikringe46/Image-Caption-Generator/blob/main/images/download.png?raw=true)


---------------------Actual---------------------<br>
start little girl covered in paint sits in front of painted rainbow with her hands in bowl end<br>
start little girl is sitting in front of large painted rainbow end<br>
start small girl in the grass plays with fingerpaints in front of white canvas with rainbow on it end<br>
start there is girl with pigtails sitting in front of rainbow painting end<br>
start young girl with pigtails painting outside in the grass end<br>
--------------------Predicted--------------------<br>
start girl sitting in front of rainbow in it end<br>
![img2](https://github.com/pratikringe46/Image-Caption-Generator/blob/main/images/download_2.png?raw=true)


