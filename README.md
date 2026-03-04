The following material is part of Erica Brisigotti's Master thesis project, titled Intensive Care outcome prediction with Machine Learning.

Weaning from mechanical ventilation represents a major clinical challenge in the Intensive
Care Unit (ICU), where both premature and delayed extubation significantly increase
morbidity and mortality. This thesis develops machine-learning models to predict the
outcome of 30-minute pressure-support Spontaneous Breathing Trials (SBTs) using physiological
time-series data. The study is based on a retrospective dataset that is broader
than most prior weaning-specific ML studies, encompassing all three weaning-difficulty
groups from a general ICU population rather than a narrow clinical cohort. 

The input data consist solely of routinely collected monitoring signals, enabling future clinical implementation
without requiring laboratory results or historical medical information.
The dataset required extensive reconstruction to address missing patient identifiers, fragmented
stays, variable sampling rates, and gaps in monitoring data. After homogenizing
signals to a 30-second sampling grid and extracting valid SBTs, three feature-engineering
strategies were evaluated: handcrafted statistical descriptors, PCA-derived components,
and latent features from convolutional Autoencoders and Variational Autoencoders. A
deliberately compact Feed-Forward Neural Network served as classifier across all feature
types, allowing the comparison to isolate the effect of representation learning. Models were
trained on an artificially balanced dataset and evaluated on a chronologically independent,
imbalanced test set using AUC-ROC, precision, accuracy, and threshold optimization.

Results show that handcrafted features provide limited predictive value, whereas PCA and
especially AE/VAE embeddings achieve higher ROC-AUC and improved generalization.
These findings highlight the importance of unsupervised feature extraction for capturing
nonlinear physiological dynamics. By relying on short pre-SBT physiological windows
(often as brief as 15 minutes) making directly at the clinical point of extubation, offering
a lightweight, readily deployable tool for ICU weaning assessment.
