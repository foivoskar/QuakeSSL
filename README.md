# QuakeSSL
An experimental workflow for classifying the type of earthquakes using Self-Supervised Learning

<a href="https://doi.org/10.5281/zenodo.14015592"><img src="https://zenodo.org/badge/881168551.svg" alt="DOI"></a>

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

The workflow was tested for events occurred from 2023-1-7 to 2024-30-6 worldwide, with magnitudes from 6 to 7. Two different datasets where obtained for thresholds of 20 and 45 (in Step 2). The waveforms were taken for the iasp91_2s model in epicentral distances of 5, 10, and 15 degrees and backazimuths of 0, 45, and 90 degrees.

The respective generated catalogs, map figures, and seismograms are available in the directory: [Dropbox link](https://www.dropbox.com/scl/fo/bs5cx8jwss07eooz1u0cl/AJjOaEbZwBY_aG0AT4tHcaA?rlkey=am9ab5m22tks7sb9g26gjdvo8&dl=0).

The results depend strongly on the polarisation pattern of the focal mechanisms and they are more accurate for one or another earthquake type depending the component that is used (among Z, N, E for backazimuths of 0, 45, and 90) and the frequency range of the filtering. Further evaluation is necessary for an analysis of the performance, depending these parameters.
