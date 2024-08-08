# First Level fMRI Data Analysis in MATLAB

To conduct first-level fMRI data analysis using MATLAB, you will need to follow several steps, including acquiring the necessary data, preprocessing it, and setting up the analysis parameters. Below are the steps and the types of data you will need, along with instructions on how to get this data into MATLAB.

### Types of Data Needed

1. **Functional MRI (fMRI) Data**: Time-series data of brain activity acquired during an experimental task.
2. **Structural MRI Data**: High-resolution anatomical scans of the brain.
3. **Onset/Timing Files**: Text files specifying the timing of experimental conditions or events.
4. **Movement Parameters**: Files capturing the head movement during the scan (typically derived from preprocessing steps).


## Step 1: Import Neuroimaging Data 

You can use fMRI data from in-house or public data sets
- **Public Datasets**: Websites like [OpenNeuro](https://openneuro.org/), [Human Connectome Project](https://www.humanconnectome.org/), and [ADNI](http://adni.loni.usc.edu/) offer publicly available fMRI datasets.
- **In-house Data**: Data collected using your own fMRI scanner.

For this tutorial, we will be using data from OpenNeuro. 

### Access OpenNeuro Dataset
1. Go to [OpenNeuro](https://openneuro.org/) and choose a dataset, such as "ds000114".
2. Download the dataset using the provided options, such as `datalad` or direct download.

#### Install and Set Up Datalad (if needed)

Install `datalad`. Download the dataset using `datalad` and navigate to the dataset directory. Get the dataset contents recursively.

```bash
# Install datalad
pip install datalad

# Download the dataset
datalad install https://github.com/OpenNeuroDatasets/ds000114.git
cd ds000114
datalad get -r .
```

### Importing Data into MATLAB

Launch MATLAB. You may need to use the `unzip` function to extract the dataset if it is compressed. You will then add the dataset directory to MATLAB's search path using the `addpath` function. Define the path to the dataset. List the files in the dataset and Display the first few files.

```matlab
% Define the path to the dataset
dataPath = '/path/to/ds000114';

% List files in the dataset
fileList = dir(fullfile(dataPath, '**', '*.nii'));

% Display the first few files
disp(fileList(1:5));
```

## Step 2: Run Preprocessing Scripts

The preprocessing pipeline includes slice-time correction, motion correction, coregistration, normalization, and smoothing.

### Download the Preprocessing Script
*Download the `preprocess.m` script from the [SPM_fMRI_Example_Pipeline repository](https://github.com/phildean/SPM_fMRI_Example_Pipeline/blob/master/preprocess.m).*

### Run the Preprocessing Script

Add SPM to the MATLAB path. Define the path to the preprocessing script. Open the script in MATLAB *and modify file paths and parameters as needed to match the downloaded dataset.* Run the script by typing *`preprocess`* in the MATLAB command window.

```matlab

% Add SPM to MATLAB path
addpath('/path/to/spm12');

% Define the path to the preprocessing script
preprocessScript = '/path/to/preprocess_batch.m';

% Run the preprocessing script
run(preprocessScript);
```


## Step 3: Run a First-Level Analysis Batch Script

### Download the First-Level Analysis Script
*Download the `firstlevel_analysis.m` script from the [SPM_fMRI_Example_Pipeline repository](https://github.com/phildean/SPM_fMRI_Example_Pipeline/blob/master/firstlevel_analysis.m).*

### Run the First-Level Analysis Script
Define the path to the first-level analysis script. Modify the script to match your data paths and experimental design. Execute the script in MATLAB by typing `firstlevel_analysis`..

*The script will ... to determine ... .*

```matlab
% Define the path to the first-level analysis script
firstLevelScript = '/path/to/first_level_batch.m';

% Run the first-level analysis script
run(firstLevelScript);
```


## Step 4: Run a Group-Level Analysis Batch Script

### Download the Group-Level Analysis Script

First, ensure all first-level analysis results are in a common directory. Then, *Download the `secondlevel_analysis.m` script from the [SPM_fMRI_Example_Pipeline repository](https://github.com/phildean/SPM_fMRI_Example_Pipeline/blob/master/secondlevel_analysis.m).* *Modify file paths and parameters in the script to point to your first-level results.*

### Run the Group-Level Analysis Script

Define the path to the group-level analysis script. Run the `secondlevel_analysis` script in MATLAB.

*The script will perform a one-sample t-test across all subjects' data to determine significant brain activation.*

% Define the path to the group-level analysis script
groupLevelScript = '/path/to/group_level_batch.m';

% Run the group-level analysis script
run(groupLevelScript);


## Resources and References
- [SPM12 Documentation](https://www.fil.ion.ucl.ac.uk/spm/doc/)
- [OpenNeuro](https://openneuro.org/)
- Example scripts and tutorials from the provided links:
  - [SPM MATLAB Scripting Tutorials by Janina Sheunis](https://jsheunis.github.io/2018-06-28-spm12-matlab-scripting-tutorial-3/)
  - [Andy's Brain Blog: Running SPM First-Level Analyses from Batch Scripts](https://andysbrainblog.blogspot.com/2014/06/running-spm-first-level-analyses-from.html)
  - [SPM fMRI Example Pipeline by Phil Dean](https://github.com/phildean/SPM_fMRI_Example_Pipeline/tree/master)
