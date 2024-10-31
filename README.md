# QuakeSSL
An experimental workflow for classifying the type of earthquakes using Self-Supervised Learning

---------------------------------

This is an experimental project for the use of seismic data and an SSL workflow. The scope is to make an algorithm where the user feeds with waveforms of pre-identified earthquake types (strike-slip, normal, and reverse) and then the algorithm attemts to classify and accordingly label other events by their waveforms. The workflow is developed in 4 steps.

### Step 1

The user makes the initial seismic catalog. Using the 1st step script, based on pyGCMT, the user creates a collection of GCMT solutions in a unique file and the map with the focal mechanisms in the desired region of interest.

### Step 2

Using the information from the GCMT solutions, the events are categorized into distinctive types (strike-slip, normal, reverse) and unclassifiable, when such a classification is not feasible. The user controls the tolerance of this classification with a threshold variable, which controls the error bar relevant to the inclination of the rake.

### Step 3

For any given collection of GCMT solutions, obtained from Step 2, synthetic waveforms for the respective events are generated and archived accordingly.

### Step 4

The final step, where the user defines the percentage of available identified events that should be used for training the algorithm, or the option to use different thresholds (see Step 2) with the lower serving for training the algorithm and a second with higher threshold to be classified. 

----------------------------------

## Results
