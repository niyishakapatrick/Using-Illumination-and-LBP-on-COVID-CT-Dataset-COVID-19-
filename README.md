# Using-Illumination-and-LBP-on-COVID-CT-Dataset-COVID-19-
Using Illumination, LBP and Machine Learning techniques on COVID-CT-Dataset( COVID-19):



## <span style="color:blue">*Assuming that Covid+ images will introduce/modify some edges/intensities/colors that are not found in Covid-images*</span>.
# 1. We convert image from Gray/RGB to YCbCr
### Y<--Luma : Give info about intensity
### CbCr <--Chroma : info about colors

Most modification clues which can not be detected by the naked eye, are hidden in the chromatic channel since the human visual system is more sensitive to overall intansity Y changes than to colour ** CbCr** changes.
# 2. Apply an edge-preserving filter to Y <--Illumination

Maxi and Mini filters behave like an edge-preserving filter such that clear edges are kept between surfaces under different lighting conditions, and details within a single surface are blurred.(You can aslo try bilateral filter from cv2 and check the results)
# 3. Compute LBP for (illumination, Cb and Cr)

Assuming that **Covid+ image** introduced the image texture modifications that are not found in **Covid- images**. LBP will help to capture texture information
# 4. LBP histogram is used as feature vector on classifiers(SVM, LDA, KNN, LR, DTree, NBayes)

# 5.Sample output
Prediction Duration: 0:00:00.085254
<span style="color:blue">*
LogisticRegression Model accuracy is:  0.84
Tree Model accuracy is:  0.91
KNN Model accuracy is:  0.89
LDA Model accuracy is:  0.86
NBayes Model accuracy is:  0.91
SVM Model accuracy is:  0.85
Random forest Model accuracy is:  0.91
*
</span>