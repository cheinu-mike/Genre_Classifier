# Genre_Classifier
Genre classification using Tensorflow with Keras

See part 5 to see the neural net architecture and training and part 6 for discussion of the results.

## Music Prediction
To run the Music predictor you can choose to download a youtube song via **music_downloader.ipynb** and then run **music_predictor.ipynb**. I have separated the files due to packaging conflict but you can use your own songs as well if you like. You must have **streaming_music_extractor** from AcousticBrainz in order to extract the spectral data from the mp3 file.

Also, I noticed that in order for the model to work, you must have tensorflow-gpu enabled or else this will result in a nan matrix. 

I have tested this with numerous songs mostly with success, it does seem to fail with more "obscure" genres such as Dream-Pop where the model thinks it's more Heavy Metal probably due to distortion. 

The last song analyzed was "Lipslap" by "Kero Kero Bonito" and the results are in music_predictor.ipynb.

## Genre mapping to gid
This should be contained in final_genre.parquet unless I have made a mistake.

The way it works is that the index of an array/list indicates the genre itself and the number inside is the normalized "counts" from people voting for that genre tag from MusicBrainz. The votes/counts are used as probabilities to deal with the issue of multigenres.
