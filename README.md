# Machine-Learning-Final-Project

## ST443: Group Project

## Task 1: multiclass classification

The first part of this project involves applying statistical machine learning techniques to
a multiclass classification problem, using the dataset provided on Moodle as a compressed
CSV file, data-1.csv.gz.
### 1.1 Data description
In the first task, you will work with hyperspectral data. This satellite image data comprises
calibrated surface-reflectance measurements for each pixel across many narrow, contiguous
spectral bands spanning the visible to short-wave infrared (approximately 420 − 2450 nm).
Compared with RGB or standard multispectral imagery, the dense spectral sampling provides
diagnostic features that support material and vegetation discrimination at the pixel level.
The data, data-1.csv.gz, covers a snapshot of an alpine region in Tyrol, Austria1 and
originate from EnMAP (Environmental Mapping and Analysis Program), a German imagingspectroscopy mission (Guanter et al., 2015). Each of the n = 218680 observations corresponds to a single pixel spectrum. The features Band i (i = 1, . . . , 218) contain reflectance
values for that pixel in the ith wavelength band. For spatial reference, the features p x, p y
record the pixel’s x, y position in a planar coordinate system. The label land type defines
eight vegetation regions present in the scene. Figure 1 shows the image, the corresponding
hyperspectral data, and the labelled regions.
The task is pixel-level classification: learn a mapping from hyperspectral pixel spectra
to the eight vegetation classes. Due to the large file size, it is recommended to read the
compressed file directly into R or Python, for example, by using the command
read.csv("data-1.csv.gz"). Given the computational load imposed by the large dataset,
you may have to train your model on a subset of the data or adopt an alternative approach,
including methods not covered in the course.
1The raw satellite data can be accessed at: https://www.enmap.org/data_tools/exampledata/
### 1.2 Task
This task consists of the following sub-tasks:
- T1.1 Explore the data to generate summary statistics and plots that help the reader understand the data, with a focus on information relevant to the classification task.
- T1.2 Train and evaluate the following classifiers (covered in the course):
• Linear Discriminant Analysis (LDA)
• Logistic classifier
• Quadratic Discriminant Analysis (QDA)
• Nearest Neighbor Classifier (k-NN)
• Gradient Boosting Decision Trees (GBDT)
• Random Forest
• Support Vector Machine (SVM)
Additionally, train and evaluate these classifiers using PCA with 10 components.
- T1.3 Summarise the classification performance of T1.2 with appropriate summaries or visualisations.
- T1.4 In glaciology and climate research, an important task is monitoring glacier extent over
time. Using the provided hyperspectral satellite data, frame glacier-ice detection as a
binary task with glacier ice = positive and all other land types = negative. Choose
and justify an evaluation metric appropriate for this setting (e.g. F1 with glacier as
the positive class). Train and evaluate three classifiers of your choice with the goal of
improving your chosen performance metric. You may use any classifier or combination
of methods covered in the course, including those listed in T1.2, as well as methods
like bagging, boosting, and regularisation.

## Task 2: feature selection
The second part of the project focuses on achieving high classification accuracy using a
minimal number of features. You will use the dataset provided on Moodle as a compressed
CSV file: data-2.csv.gz.
### 2.1 Data description
The dataset contains high-dimensional neural activity recordings from the mouse frontal
cortex during a multisensory decision-making task. In this task, mice were trained to respond to visual and auditory cues presented simultaneously, using these sensory inputs to
decide whether to turn a wheel to the left or right to obtain a reward. The dataset consists
of trial-by-trial spike count features extracted from two Neuropixels probes simultaneously
recording from hundreds of neurons. The recordings originate from a session in the International Brain Laboratory’s brain-wide map study (mouse ID: KS094, session date: 2022-06-15,
International Brain Laboratory et al., 2023), and have been preprocessed to align spikes to
the onset of each trial’s visual stimulus. For each trial, spike counts were computed in five
consecutive 100 ms bins covering the 0–500 ms window after stimulus onset, resulting in
temporally resolved population activity. Each neuron contributes one feature per time bin.
The dataset has p = 11190 features in total (2238 neurons ×5 time bins), measured across
n = 683 trials. Each row corresponds to a single behavioural trial, and each column corresponds to the spike count of a particular neuron in a specific time bin. Column names follow
the pattern unit i bin t, where i is the neuron index and t is the time bin index (from 0 to
4). The label variable label indicates the animal’s binary choice on that trial: “Left” (0) or
“Right” (1). Trials with no response have been excluded. The neural and behavioural data
were accessed through the IBL’s ONE API (Alyx team and International Brain Laboratory,
2020). Due to the large feature dimensionality, it is recommended to read the compressed file
directly into R or Python, for example, by using the command read.csv("data-2.csv.gz").
##2.2 Task
This task consists of the following sub-tasks:
- T2.1 Explore the data to generate summary statistics and plots that help the reader understand the data, with a focus on information relevant to the classification task.
- T2.2 Train and evaluate feature selection methods with the goal of achieving high balanced
accuracy using a minimal number of selected features. Use three different approaches
of your choice that were covered in the course.
- T2.3 Train and evaluate up to three additional feature selection methods, other than those
in T2.2, which may include methods not covered in the course, with the goal of
achieving high balanced accuracy using a minimal number of selected features. Provide
an explanation of each new method.
- For T2.2 and T2.3, your evaluation results should include the balanced accuracy
and the number of selected features achieved by each method for various numbers of
selected features. You may also compare the balanced accuracy achieved by different
methods for a similar number of selected features. S
