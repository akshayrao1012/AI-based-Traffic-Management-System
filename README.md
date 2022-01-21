# AI-based-Traffic-Management-System

###  :wrench: This repository is currently in progress :hammer: 

## Abstract

In this fast-paced world where everything is powered with technologies like AI, some systems were automated but never really were included in the AI space. One such example is that of the traditional traffic management system. Since childhood we have seen the same traffic signal that works at a set time by the traffic authorities. Nothing much has changed since the invention of these signals. While all the appliances and machines are now powered using AI, the traffic system still runs in the traditional way. This led us to explore the idea of building a smart traffic management system, where the idea is simple but the impact is tremendous. According to one of the posts, an average citizen wastes around 20-25% of time waiting at a signal in the US. This number would be quite high in countries like India, considering narrow roads and a substantially heavy number of vehicles. Even though the number looks small but 
when multiplied with the number of commuters, this problem is worth addressing even if the number is reduced by even a small ratio. 

Currently we have CCTV cameras available at most of the highway signals. With the growing trend of 5G and IoT, we can expect an increase in more sensors along with CCTV images that can combine to provide additional traffic information / dataset about traffic density, which can answer the peak hours, accidents, traffic slowdown issues etc, types of vehicles, frequent defaulters etc.

## Problem Definition

Our focus would be on vehicle detection within a defined boundary, classifying them into small, medium and large vehicle categories. Further extending it, we would be focusing to determine/predict the vehicle counts and quantify the traffic conditions that can help traffic management systems. Example - optimise the traffic light duration with respect to the number of vehicles.
In this project, we have focused on using advanced computer vision methods that shall use Real-Time image/video processing and extract valuable features and information. 
We look forward to reducing the traffic duration by identifying the number of vehicles. This system not only solves the traffic issue but also the data retrieved from this system will be used to monitor and manage traffic more efficiently.

## Literature survey

To meet the above requirement in solving the problem, we have various CNN models available with various architectures differing in the image processing methods which are trained in open image dataset and various regularization techniques. We will be attempting to use transfer learning techniques to use these models that will give better accuracy/precision to our recorded datasets. 
Vehicle detection can be a problem when the images are captured in different time periods of the day or different weather conditions.
Defining the region of Interest to limit the object detection in defined boundaries and help the traffic management system to evaluate traffic density and/or corresponding action. 
Keeping above points, we went through literature surveys that can best answer and mitigate the possible issues.  
The literature study went into studying the advanced computer vision methods on CCTV data [7] which uses pre-trained Faster-R-CNN ResNet model fine-tuned with 700 CCTV images and able to identify even small vehicles in the image background. This study provides the framework categorized in two parts: one - capturing CCTV images from six stationed cameras, using Faster R-CNN model and providing current state of traffic volume (Vehicle count); second – These data is then fed for prediction analysis. The literature shares four kinds of approaches – naïve, parametric, nonparametric and enhanced nonparametric. Naïve works [16][18] on past traffic behavior that limits prediction during abnormal situations. Parametric approach [18][19] 


uses analytical and traffic-based simulation methods, mathematical equations derived from traffic theory. Typical nonparametric approaches primarily include: Kalman filtering [20]; support vector regression (SVR) [21]; random forest (RF) regression [22]; and traditional artificial neural networks (ANNs) [23]. Enhanced nonparametric approaches primarily include recently developed deep learning RNNs. LSTM is one of the most widely implemented RNNs for traffic analysis, especially after the study in [24]. LSTM is specifically designed to memorize long-term dependencies [25].
Further we extended our study in recent models in real time vehicle detection and classification. In this, the research papers [1] appreciates using YOLOv3 compared to Faster R-CNN /SSD. Further papers [3] provide an approach using Yolov4 for video dataset with results comparable using Yolov3 on image dataset. Yolov4 is proven to provide the best speed and accuracy [27].

## Data collection

The time when this project began was in the midst of a pandemic and stepping out during the lockdown is considered to be a criminal offense. In such a situation, the only way to gather data was through the internet. One of the sites that we came across was earthcam.com that had live cameras at different locations of the world. The images and videos used for this project are primarily taken from this website and only earthcam.com hold rights towards the content. The video captured from this website is solely for educational and research purposes and in no way will be used in a negative way.  We have discussed this with our mentor and taken approval for the same. We have recorded a few videos/images which had a top view of moving/stalled vehicles at the traffic signal. We have captured from various sources on the internet and will be testing on those videos/images as well. We did try collecting data from the local toll plaza/traffic management team, however we were informed that we would be needing special permissions to go ahead with the same.

## EDA

As mentioned above, we have used snippets of live traffic cams from earthcam.com. These snippets are broken down into frames at specific intervals of time(t1). Then they are given a region of interest(ROI) and are fed to the algorithm for detection(using YOLO) to get the number of vehicles halted at the signal.

The images are of 1280x720 pixels and 1 to 1.5 mb in size. We have taken 100-125 images for feeding the model as of now. These images contain 3 different classes of vehicles for detection, particularly small, medium and large based on the dimension of the vehicle. They are annotated using labelImg tool. 

The video quality prerequisites include video captured at 30fps with 1280x720 pixels. Normal CCTV cameras come in the range of 1,2,5 MP. For our application we will be needing a minimum of 2 MP for the clarity of vehicles for the model to detect with less errors. 
