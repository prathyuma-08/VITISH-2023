# VITISH-2023
An internal hackathon for Kavach 23
# Obscene Media Detection Solution
PS ID: KVH-002
Title of PS: Obscenity blocker solution

## Problem Statement
Design and develop a technological solution for identifying and blocking any obscene media (image/video/audio) at the user’s end.The solution should be able to send alerts to the concerned nodal agency in case of the spread of such content. The solution may be in the form of a desktop/mobile application or a web browser plugin.

## Complexity of the Problem
* Finding a suitable dataset for training the models was challenging as there is no public dataset available for obscene media.
* The project involves developing models to classify between safe and unsafe media content across the website in various formats, including audio, gif, images and videos.
* The implementation of the solution requires the use of deep learning frameworks and techniques.

## Novelty of the Project
* We are working towards using ensemble learning approach to use Nudenet and Open NSFW models. But these models were not been updated by the authors for past couple of years. The dependency and vectors have become incompatible and we are still trying to revive it. A sample implementation has been done with Inception V3 model which gives around 95% accuracy.
* The project also involves scraping images from porn sites to obtain more data. The GAN model is used to upscale the images for better classification accuracy.
* The solution incorporates the use of frame-by-frame checking for video classification, which increases the accuracy of the model on a real time basis.

## Feasibility
* The use of browser extensions as a technological solution is highly feasible due to the widespread use of web browsers.
* The implementation of the solution only requires the user to install the browser extension, making it easily accessible and user-friendly.
* The solution can be integrated with other existing applications or websites, making it even more versatile.

## Scalability
* The use of browser extensions allows for easy scalability as it does not require any additional infrastructure or resources.
* The solution can be easily updated or improved by modifying the code within the browser extension.
* The solution can also be deployed across multiple platforms, making it highly scalable.

## 2 Major Modules 

* Image clasification 

Trained on Inception V3 with 2 classes based on " The Image and video dataset for adult content detection in image and video " .The model classifies image/video/gif/svg into Safe and Unsafe .The model perfomed well with around 95% accuracy with just 10 epocs for priliminary rounds .
> noktedan, ali (2021): The Image and video dataset for adult content detection in image and video. figshare. Dataset. https://doi.org/10.6084/m9.figshare.14495367.v1

* Image detection

This module helps the extention decide which type of NSFW tag a specific content belongs. It has 5 classes namely Normal, Nudity, Sexual Activity, Lingerie, Gore images. These images were scrapped using BeautifulSoup and manually segregated into folders. Upsampling has been done using regular data augumentation methods like zooming, rotation, sheering, horizontal flip, height shift, width shift, fill mode. This upsampled data is trained using Inception V3.

```
rotation_range=40,
width_shift_range=0.2,
height_shift_range=0.2,
shear_range=0.2,
zoom_range=0.2,
horizontal_flip=True,
fill_mode='nearest'
```

## Future works 

The current model only uses Inception V3 with around 95% accuracy. Combining the two NSFW pretrained detection models, OpenNsfw Model and Nudenet, can potentially improve the accuracy of the system and cover a wider range of NSFW content. Both models are designed for NSFW (Not Safe for Work) classification, with Nudenet being specifically designed for obscenity detection and OpenNsfwModel being a more general-purpose NSFW classifier. By combining these two models, we could potentially improve the accuracy of the detection system and cover a wider range of NSFW content.

## Usage
To use the solution, simply download and install the browser extension on your preferred web browser. Once installed, the solution will automatically scan and classify any media viewed on the browser. If any obscene media is detected, an alert will be sent to the concerned nodal agency for further action.

## Conclusion
The obscene media detection solution is a novel and feasible solution to a complex problem. The use of ensemble learning, frame-by-frame checking, and scraping actual image porn sites has increased the accuracy of the model. The use of browser extensions makes the solution easily accessible and scalable, making it a versatile solution for identifying and blocking any obscene media.
