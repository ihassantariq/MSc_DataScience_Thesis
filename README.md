# Analysis and Classification of 12 channel ECG signal using Edge Computing


### Introduction

The design of advanced health-monitoring systems has always been a topic of active research. During the past decades, numerous portable devices have been introduced for the early detection and diagnosis of heart failure, since it is a common, costly, disabling, and deadly syndrome. Advanced heart-monitoring devices are capable of providing reliable, accurate heart monitoring
and are able to detect sporadic events during periods of time when things would otherwise be unclear. Functioning as a black box, these devices have the potential to enhance the decision-making process, by notifying doctors when patients need readmission and in this way constituting an effective alternative capable of saving patients’ lives. \cite{a12020032}.

Research on artificial intelligence (AI), and particularly the advances in machine learning (ML) and deep learning (DL) have led to disruptive innovations in radiology, pathology, genomics and other fields. Modern DL models feature millions of parameters that need to be learned from sufficiently large curated data sets in order to achieve clinical-grade accuracy, while being safe, fair, equitable and generalising well to unseen data. \cite{Rieke_2020}

Data storage and model training occur on these models usually on high-performance cloud servers in conventional centralized ML approaches. Multiple edge nodes also collaborate with the remote cloud to perform large distributed tasks that include both local processing and remote coordination and execution. Traditional model of cloud computing is unsuitable for applications that demand low latency, so as a result a new model of computation termed edge computing has sprung forth. Edge computing is primarily concerned with transmitting data among the devices at the edge, closer to where user applications are located, rather than to a centralized server. Edge node (or edge client, edge device) is usually the resource-constraint device that
end user uses and it is geographically close to the nearest edge server,
who has abundant computing resources and high bandwidth communicating with end nodes. When the edge server requires more computing power, it will connect to the cloud server. \cite{fedrated_learning_as_edge_computing}. 


Federated Learning (FL) is a concept developed by Google researchers in 2016, as a promising solution for addressing the issues of communication costs, data privacy, and legalization. An FL approach is a distributed ML approach where models are trained on edge devices, organizations, or individuals under centralized control without sharing their local datasets. This ensures the privacy of data during the training process. An edge server or cloud server periodically gathers the trained parameters to create and update a better and more accurate model, which is sent back to the edge devices for local training. \cite{s22020450}

As in case of health data, which has privacy concerns, FL allows collaborative insights without transferring patient data outside of the institutions’ firewalls. Instead, each participating institution’s ML process takes place locally, with only model weights being share. Recent research has shown that models trained by FL can achieve performance levels comparable to ones trained on centrally hosted data sets and superior to models that only see isolated single-institutional data. \cite{Rieke_2020}


### Summary

In the end, the categorization of 12-channel ECG arrhythmias was improved by using oversampling (and undersampling) approaches. Random Oversampling (ROS), in particular, performed admirably. The latter showed a considerable increment compared to the model trained with the original data. Although SMOTE performed well in a variety of cases, ROS was chosen as the best strategy due to its ease of implementation.

In conclusion, Catboost with the random oversampling technique was the best model but we cannot deploy that in mobile devices which support both Android/IOS as well as the XGBoost ROS model. DNN ROS, LSTM and Team \# 20 model can be deployed to mobile devices easily and perform better with the same accuracy and F1-Score. Any model that is built using Matlab Deep Learning Toolbox, Pytorch framework which can be exported to ONNX and Tensorflow Keras library and Tensorflow itself can be converted to Tensorflow Lite and we can see them in action in the above demo \ref{modelsdeployment}. Inferencing big models like Team \#2 and Team \# 20 models takes a lot of time to get the output after conversion. 

As far as Federated Learning is concerned, the DNN trained with ROS (oversampled) data proved to be the best model in the setting of FL. The latter had an Overall Index of 0.55 and an F1-Score of 0.55. Even said, when more than four local nodes were included, utilizing an LSTM with oversampled data produced more consistent results. Then LSTM is the recommended model to implement within this data when the number of nodes is large. On the other hand, DNN with ROS data is the candidate to select when dealing with a small number of clients.


