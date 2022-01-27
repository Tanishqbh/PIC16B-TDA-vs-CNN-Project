# PIC16B - TDA-vs-CNN-Project

# Project Proposal
### Abstract
In this project, we will compare the effectiveness of a topological data analysis based approach to biomedical image classifciation to that of more traditional image classifiers. Specifically, we hope to verify and potentially improve upon the results of the paper *Topological data analysis of high resolution diabetic retinopathy images* (the full paper is available at https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0217413). In the paper, the authors generate persistence landscapes through applying a graysclae filtration to diabetic retinopathy images, and this topological data is then fed to a support vector machine in order to classify the images. In this project, we will first reimplement the paper's metholodology using Python and then also compare the results of this methodology to a more traditional image classifcation approach via a convolutional neural network.

### Planned Deliverables
In the original paper, the authors used data from a single source and had only an incredibly small amount of data to work with. Since then however, many more high-resolution images of diabetic retionpathy have become publically available. Thus, the first step of the project will be to combine these data sets, as using a larger and more diverse dataset should lead to more robust classifiers. Combining and working with these large data sets will likely require the use of methods such as SQL databases. Further, the data will need to be processed and suitably cleaned.

Then, we will need to build an interface such that, for an inputted image, a suitable simplicial complex is built based upon a grayscale level filtration. We will then use an open-source topological data analysis library to generate summary statistics for these complexes. These summary statistics will then be used to train a support vector machine in order to classify the images. (Notably, the original paper does not provide any code, so we will attempt to replicate the paper's methodology as best possible based upon their 'Materials and Methods' section.) Further, a convolutional neural network will also be trained on the image data and the results of the two image classification methodologies will be compared. In addition to generating visualizations of the results of the two models such as decision regions, we hope to also build an interactive visualization that will aid people unfamiliar with algebraic topology to intuitvely understand the methodology behind topological data analysis.

Lastly, should the paper's claim that the topology-based methodology matches the performance of neural network based methods be found not to hold, then, if time permits, we may also attempt to implement more sophisticated topological methods that may acheive better results. For instance, the use of mutliparameter barcodes or persistence images may prove to be more robust than the original paper's methods.

The code and the results of the topology-based and neural network-based classifier will be presented in a Jupyter notebook.

### Resources Required
We will first require high-resolution diabetic retinopathy image data. For this, we can use the same data the original authors use, which is available here: https://www5.cs.fau.de/research/data/fundus-images/ . Further, in order to build a more robust model, we will be combining this with other publically available datasets, such as this one: https://www.sciencedirect.com/science/article/pii/S2352340921003528 .

Further, working with these large image datasets may also require the use of vast amounts of computing power.

### Tools and Skills Required
This project will require the use of several of the skills taught in PIC 16B. For instance, we will need to combine and then clean disparate data sets. We may also need to use packages such as TensorFlow and OpenCV in order to perform our convolutional neural network based image classification. In addition, we will use interactive data visualization packages such as Plotly both to display the results of the image classification models as well as to explain the methodology behind persistent homology.

Further, we will also need to learn to work with opensource software on GitHub. For instance, we will need to gain familiarity with Python-based topological data analysis packages such as the GUDHI library.

### What You Will Learn
One of the learning goals of this project will be to gain familiarity with actual implementation of topological data analysis tools, such as persistence landscapes. Further, I'll need to learn to work with image data, which is not something I've previously done. As an extension of this, I'll also need to learn about computer vision and convolutional neural networks.

### Risks
It's possible that working with large image-based datasets requires more computational power than is available on a single laptop. In this case, it may be necessary to work on-campus and use UCLA's servers. Additionally, it's possible that the disparate datasets we plan to combine do not play well with each other. In this case, we may for instance perform the topological summary statistics on each of the data sets indiviudally before inputting the results to a support vector machine.

### Ethics
In commerical application, its necessary for a biomedical image classifier to be incredibly robust, as it could otherwise potentially lead to misdiagnosis. However, this project focuses largely on the comparison of methodologies, so this is not an immediate concern.

More practically, its possible that our dataset is not diverse enough. Even though we will be combining several datasets, this will still only reperesent the data collected at a few hospitals. Thus, its possible that if ethnic or racial factors influence diabetic retinopathy, then our models may in fact be less robust in actual practice than indicated by scores on our test data.

### Tentative Timeline
In the next two weeks, we hope to have procured, reshaped, and cleaned our datasets as needed. This time will also be used to learn more about the conceptual ideas behind diabetic retinopathy as well as on topological data analysis and convolutional neural networks.

In four weeks, we hope to have built our interface that will allow topological summary statistics to be extracted from the input images. These summary statistics will also be used to train and test a support vector machine and the original image data will also be used to train and test a convolutional neural network.

In six weeks, we hope to generate interactive data visualizations of both the results of the models as well as of an intuitve explanantion of persistent homology. If all of the aforementioned steps are completed on time, then we will also implement and compare the results of more sophisitcated topological image classifiers, such as persistence images.
