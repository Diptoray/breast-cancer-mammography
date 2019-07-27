# Breast cancer mammography analysis and prediction of malignancy
Predicting breast cancer malignancy based on patient and mammographic mass data

Summary : This project aims to create a deep learning model using Tensorflow and Keras to predict whether a breast tumour is benign or malignant based on patients' personal data as well as data about the mammographic mass(the tumour) itself.
10-fold cross validation has been used to compute the results, with accuracy being the metric. The best result obtained was an accuracy of 80.4% after 100 epochs , where an accuracy of 80% was previously determined to be a good result by experts.

The actual dataset can be found in the text file 'mammographic_masses.data.txt', whereas a detailed description of the dataset's contents can be found within the text file 'mammographic_masses.names.txt'. The actual solution, including all the Python code, can be accessed by opening the file 'DeepLearning - Predicting the malignancy of a mammogram mass.ipynb', which is an IPython notebook which can be accessed via a terminal window, or through a Jupyter notebook,software platforms like Anaconda or GPU server services like Google Colab and others.

We'll be using the "mammographic masses" public dataset from the UCI repository (source: https://archive.ics.uci.edu/ml/datasets/Mammographic+Mass)

This data contains 961 instances of masses detected in mammograms, and contains the following attributes:

   1. BI-RADS assessment: 1 to 5 (ordinal)  
   2. Age: patient's age in years (integer)
   3. Shape: mass shape: round=1 oval=2 lobular=3 irregular=4 (nominal)
   4. Margin: mass margin: circumscribed=1 microlobulated=2 obscured=3 ill-defined=4 spiculated=5 (nominal)
   5. Density: mass density high=1 iso=2 low=3 fat-containing=4 (ordinal)
   6. Severity: benign=0 or malignant=1 (binominal)
   
BI-RADS is an assesment of how confident the severity classification is; it is not a "predictive" attribute and so we will discard it. The age, shape, margin, and density attributes are the features that we will build our model with, and "severity" is the classification we will attempt to predict based on those attributes.

Although "shape" and "margin" are nominal data types, which sklearn typically doesn't deal with well, they are close enough to ordinal that we shouldn't just discard them. The "shape" for example is ordered increasingly from round to irregular.

A lot of unnecessary anguish and surgery arises from false positives arising from mammogram results. If we can build a better way to interpret them through supervised machine learning, it could improve a lot of lives.
