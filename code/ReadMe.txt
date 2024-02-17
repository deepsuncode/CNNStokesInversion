This folder contains information of the source code of our program, called CNNStokesInversion.py, which is used to infer vector magnetic fields from the Stokes profiles of GST/NIRIS. In order to execute this program, visit
https://web.njit.edu/~wangj/CNNStokesInversion/
to download all zip files in the Source Code and Datasets sections and
extract all the downloaded zip files into the same large folder, in which you see (after uncompressing the zip files) the following 9 folders: "code", "trainset", "traincsv", "testset1", "testset2", "testset3", "results1", "results2", "results3".

To run this CNN tool, enter the "code" folder.
The usage is given as follows:
	python3 CNNStokesInversion.py 1 0 0

The first argument "CNNStokesInversion.py" is the Python program file name.
The second argument "1" denotes that the program will perform Stokes inversion on the first test set in folder "testset1", which is obtained from AR 12371 collected on 2015 June 25 20:00:00 UT, and the results will be stored in folder "results1".

An alternative option is "2" ("3", respectively), which uses the second test set in folder "testset2" from AR 12665 collected on 2017 July 13 18:35:00 UT (the third test set in folder "testset3" from AR 12673 collected on 2017 September 6 19:18:00 UT, respectively), and the results will be stored in folder "results2" ("results3", respectively). The usage is given as follows:
	python3 CNNStokesInversion.py 2 0 0
	python3 CNNStokesInversion.py 3 0 0

The third argument "0" denotes that the program will load and use the pre-trained model, named "model.h5". If one would like to re-train the model, change "0" to "1".

The fourth argument "0" denotes that the program will use the preprocessed CSV files in the data folders for training and testing. If one would like to re-convert the FITS data to CSV files, change "0" to "1".

In the CSV file in the "traincsv" folder, there are 183 columns where the first three columns are labels representing Btotal, inclination angle, azimuth angle respectively, followed by 60 columns representing Stokes Q, followed by 60 columns representing Stokes U, followed by 60 columns representing Stokes V for each pixel. There are one million pixels (rows) in the CSV file.

In each CSV file in the "testset1", "testset2", "testset3" folders, there are 180 columns comprising 60 columns representing Stokes Q, followed by 60 columns representing Stokes U, followed by 60 columns representing Stokes V for each pixel. There are 518400 pixels (rows) in the CSV file.

In each CSV file in the "results1", "results2", "results3" folders, there are three columns representing predicted Btotal, inclination angle, azimuth angle (in that order) respectively for each pixel. There are 518400 pixels (rows) in the CSV file. Our program converts the CSV file to PNG files.


Our program is run on Python 3.6.8, Keras 2.2.4, and TensorFlow 1.12.0.



