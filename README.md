# Kana-Decoder
An OCR tool specifically designed to recognize and digitize handwritten Japanese characters. This project leverages image processing and machine learning techniques to accurately extract text from handwritten scripts, preserving the nuances of Japanese handwriting styles. Ideal for educational and translation applications by Creating a model that recognizing handwritten Japanese characters, including Hiragana, Katakana, Kanji, and Kuzushiji, using Tensorflow. 

## Prerequisites and Installations
Python 3 (any python3 versions should work)

Tensorflow 

Keras 

Numpy 

matplotlib (newest version)

PIL (newest version)

skimage (newest version)

sklearn (newest version)


## Getting the Data / Training your model
The data for Hiragana, Katakana, and Kanji can be downloaded from the ETL database website. The data for Kuzushiji can be found in the KMINST database. See Reference below.

`read_{hira, kana, kanj}.py` - save the whole data into one npz file 

`modify_{hira, kana, kanj}.py` - create the train_images, train_labels, test_images, and test_labels files

`{hiragana, katakana, kanji}_CNN.py` - create a h5 model

## Results

|Model   |Hiragana|Katakana|Kanji|Kuzushiji|
|---|---|---|---|---|
|Accuracy|98.4%|98.6%|98.6%|95.6%|

Note: these are the results I got after running the CNN models, results may vary slightly in every trial.

## Additional Notes
If tensorflow doesn't work at first, try running this command: `/Applications/Python 3.7/Install Certificates.command`

When converting h5 to mlmodel, downgrade keras 2.4.3 to keras 2.2.4.

To fix potential errors, run the following command:
```
tf_upgrade_v2 --infile /Library/Frameworks/Python.framework/Versions/3.7/lib/python3.7/site-packages/keras/backend/tensorflow_backend.py --outfile /Library/Frameworks/Python.framework/Versions/3.7/lib/python3.7/site-packages/keras/backend/tensorflow_backend.py
```
Also, go into the optimizers.py file within keras and manually change this in line 75:

original:`allowed_kwargs = {'clipnorm', 'clipvalue'}`

changed version:`allowed_kwargs = {'clipnorm', 'clipvalue','name','learning_rate'}`

## References
1. Electrotechnical Laboratory, Japanese Technical Committee for Optical Character Recognition, ETL Character Database, 1973-1984.
2. Tarin Clanuwat, Mikel Bober-Irizar, Asanobu Kitamoto, Alex Lamb, Kazuaki Yamamoto, David Ha, "Deep Learning for Classical Japanese Literature", arXiv:1812.01718. 
   KMNIST Dataset" (created by CODH), adapted from "Kuzushiji Dataset" (created by NIJL and others), doi:10.20676/00000341
