## Author
Name: Simon Lim

## Presentation of Data
- The dataset used for this analysis is the Flickr8k dataset, composed of 8,000 images collected from the photo-sharing website Flickr. Each image within the dataset has a corresponding caption that is annotated with five descriptive words. The images that comprise the dataset have an array of scenes, activities and objects depicted within them, whilst also being of high quality. The captions use these scenes, activities, and objects to describe these images. The dataset is organised into an images folder and a captions file. This is a widely used dataset in image captioning research, making it extremely relevant to our analysis. The diversity of images in this dataset ensures that the models are trained to handle varied contexts (Modi, 2018).

## Walk-through of Data Preparation Performed
### MobileNetV3 & LSTM
- The data preparation began by downloading the Flickr8k dataset from Kaggle using the Kaggle API. A ‘Vocabulary’ class was then created to allow for the numericalisation and tokenisation of the captions within the dataset to be handled (Pan et al., 2020). 
- The two main components were build_vocabulary, which counts the frequencies of words that occur within the captions. ‘numericalise’ uses the tokenised text from the vocabulary to then create a numerical form. The vocabulary class was used on the loaded captions to build the vocabulary of the dataset (Falconí et al., 2019). 
- A ‘Flickr8kDataset’ Class was created to ensure that each of the images and captions had been loaded into Collaboratory and that transformations were applied. The final step of the data preparation was to load the data into the designated training and testing Data Loaders for batching and shuffling (Falconí et al., 2019).

### Resnet & LSTM
- The Flicker8k dataset was downloaded and unzipped for preprocessing from Kaggle to be utilised in the image captioning model. The architecture consisted of a feature extractor for images using a CNN model which was Resnet in this case. the other part consisted of LSTM which consisted of a sequence-based model for captions generation (Rezende et al., 2017). 
- Necessary libraries and utilities were utilised for the project, involving image processing (using ResNet50 model) and natural language processing tasks (using NLTK and Keras for text preprocessing and evaluation) (Rezende et al., 2017).
![image](https://github.com/SimonLim03/Image-Captioning/assets/150989115/386afe70-ad9c-4c0c-9ff3-da460047afa0)
- The conversion of the text files to pandas dataframe was carried out for organizing and structuring the image-caption data into a format that is suitable for further processing, such as model training and evaluation. Visualisations of some images and dataframe structure was also included to understand the features of the dataset (Rezende et al., 2017).
![image](https://github.com/SimonLim03/Image-Captioning/assets/150989115/bea2f9d6-7e71-4f0a-824a-874f42a8b8a8)
- Creation of train,test and validation dictionary having key as the image id and value as a list of its captions was carried out. ResNet50 model was utilised for encoding the images to be utilised in the image captioning architecture. Encoding was carried out for images and forming dictionaries containing mapping of image_id to image encodings (Castro et al., 2022a).

## Presentation of architectures tested during experimentation and rationales. 
### MobileNetV3 & LSTM
- The testing of the Convolutional Neural Network MobileNetV3 architecture for this experiment was chosen due to its effectiveness on mobile devices whilst also achieving high accuracy results. Incorporating depth wise separable convolutions within the MobileNetV3 architecture significantly reduces the need for large parameters and the computational cost (Hossain et al., 2019a). 
These depth wise separable convolutions have a single convolutional filter within each input channel and only use a 1x1 convolution when combining the output. The other vital component of the MobileNetV3 architecture is the Squeeze-and-Excitation (SE) Blocks. This architecture component allows the interdependencies between the chances through explicitly modelling them. The whole architecture of MobileNetV3 looks to reduce the number of parameters and create a more streamlined model that is lightweight, which is a highly beneficial component (Stefanini et al., 2022). 
Long Short-Term Memory (LSTM) is a recurrent neural network that can take long-term dependencies in sequential data and allow them to be used in language modelling and prediction. The memory cells in LSTM allow the cell state to be maintained over time and allow long-term dependencies to be tracked (Geetha et al., 2020). 
There are three types of gates in LSTM that can regulate the flow of information throughout the learning process: the forget gate, the input gate and the output gate. The ability of LSTM to capture the long-term and short-term dependencies effectively is a result of the incorporation of the cell state, the long-term memory, and the hidden state, the output of the LSTM cell (Xu et al., 2017a). 
Overall, LSTMs were chosen for the experiment due to their proven ability to provide accurate and reliable results in language modelling tasks and take on sequential data, which needs to maintain the context of previous data through long sequences (Geetha et al., 2020). 

