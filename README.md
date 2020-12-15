# R-U-Smiling
:mask: Predicting facial expressions (emotions) when a person is wearing a mask

### Motivation
Many people are wearing masks these days. It sometimes becomes tough for me to sense if a person is happy or not since their facial expressions (with important emotion indicators like mouth gestures) are partially occluded. Therefore, I am curious to see if we can predict a person's emotion from upper face features (the parts that are not occluded by masks).

### Exploration
I applied the face landmark detection model from [Mediapipe](https://google.github.io/mediapipe/solutions/face_mesh) on the part of the [FEI Face database](https://fei.edu.br/~cet/facedatabase.html) which contains 400 images of neutral and smiling facial expressions (with 200 subjects). I then extracted the upper face landmarks and trained an SVM classification model based on the training data (60%). The results showed 94.2% accuracy on the validation dataset (10-fold cross-validation) and 95.0% accuracy on the testing dataset (40%). **This indicts that we can predict face expressions (emotions) from upper face features.**

However, when putting face masks onto the images in the testing data, re-training the model with mask-on images, or applying to real-world examples like myself wearing a mask in front of the camera, the model did not provide good estimations. I observed that the face landmark detection model did not offer reasonable estimates when people are wearing masks.

### Next Step
So I guess the next step is either to make the face landmark detection model more robust or to predict the facial expressions from the raw images (with a larger dataset). I also find some interesting work along the line in the research community [Zhang et al., 2018].

Ligang Zhang, Brijesh Verma, Dian Tjondronegoro, and Vinod Chandran. 2018. Facial Expression Analysis under Partial Occlusion: A Survey. <i>ACM Comput. Surv.</i> 51, 2, Article 25 (June 2018), 49 pages. DOI:https://doi.org/10.1145/3158369 
