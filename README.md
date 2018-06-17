<img src="https://github.com/ArunMichaelDsouza/tensorflow-image-detection/raw/master/icon.png" width="250" height="auto" alt="tensorflow-image-detection icon"/>

# tensorflow-image-detection
A generic image detection program that uses Google's Machine Learning library, [Tensorflow](https://www.tensorflow.org/) and a pre-trained Deep Learning Convolutional Neural Network model called [Inception](https://research.googleblog.com/2016/03/train-your-own-image-classifier-with.html).

This model has been pre-trained for the [ImageNet](http://image-net.org/) Large Visual Recognition Challenge using the data from 2012, and it can differentiate between 1,000 different classes, like Dalmatian, dishwasher etc.
The program applies Transfer Learning to this existing model and re-trains it to classify a new set of images.

This is a generic setup and can be used to classify almost any kind of image. I created a small demo that classifies two image data sets - my photos and my girlfriend's photos, and returns a prediction score denoting the possibility of it being my image or my girlfriend's image.

<br/>

## Installation
Make sure you have [Python 3](https://www.python.org/downloads/) installed, then install [Tensorflow](https://www.tensorflow.org/install/) on your system, and clone this repo.

<br/>

## Usage

### Prepare the image data sets
In order to start the transfer learning process, a folder named ``training_dataset`` needs to be created in the root of the project folder. This folder will contain the image data sets for all the subjects, for whom the classification is to be performed.

Create the ``training_dataset`` folder and add the images for all the data sets in the following manner -

```javascript
/
|
|
---- /training_dataset
|    |
|    |
|    ---- /arun
|    |    arun1.jpg
|    |    arun2.jpg
|    |    ...
|    |
|    |
|    ---- /erica
|         erica1.jpg
|         erica2.jpg
|         ...
|
|     
```
This enables classification of images between the ``arun`` and ``erica`` data sets.

> Make sure to include multiple variants of the subject (side profiles, zoomed in images etc.), the more the images, the better is the result.

### Initiate transfer learning
Go to the project directory and run -

```javascript
$ bash train.sh
```
This script installs the ``Inception`` model and initiates the re-training process for the specified image data sets.

Once the process is complete, it will return a training accuracy somewhere between ``85% - 100%``.

The ``training summaries``, ``retrained graphs`` and ``retrained labels`` will be saved in a folder named ``tf_files``.

### Classify objects

```javascript
python3 classify.py
```

This opens up the file dialog using which you can select your input file.

<img src="https://raw.githubusercontent.com/ArunMichaelDsouza/tensorflow-image-detection/master/file-dialog.png"/>

Once the input file is selected, the classifier will output the predictions for each data set. A prediction score between ``0.8`` to ``1`` is considered to be optimal.

<img src="https://raw.githubusercontent.com/ArunMichaelDsouza/tensorflow-image-detection/master/cli-output.png"/>

<br/>

## Results
<img src="https://raw.githubusercontent.com/ArunMichaelDsouza/tensorflow-image-detection/master/result.png"/>

<br/>

## Contributors

| [<img src="https://avatars3.githubusercontent.com/u/4924614" width="100px;"/><br /><sub><b>Arun Michael Dsouza</b></sub>](https://github.com/ArunMichaelDsouza)<br />| [<img src="https://avatars3.githubusercontent.com/u/11679543" width="100px;"/><br /><sub><b>Royal Bhati</b></sub>](https://github.com/royalbhati)<br />|
| :---: | :---: |

<br/>

## License
MIT License

Copyright (c) 2017 Arun Michael Dsouza

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

