# fMRI Data Analysis in MATLAB using SPM

This tutorial guides you through the process of analyzing fMRI data using MATLAB and SPM (Statistical Parametric Mapping). The focus is on scripting and using MATLAB commands rather than the SPM GUI. We will use a dataset from OpenNeuro and process it using pre-written batch scripts. *All necessary code is available on the **matlab-spm-scripts-jsh** github repository.*

The goal here is to use batch scripting in MATLAB to practice running automated pipelines that preprocess and analyze task-based fMRI data with minimal user input, using steps that one would typically have completed through the SPM12 GUI (e.g., Realign, Smooth, Segment, Specify 1st-level, Estimate, or Results).

## Prerequisites

### Install SPM
To follow this tutorial, you need to have [SPM12](https://www.fil.ion.ucl.ac.uk/spm/software/download/) installed and added to your MATLAB path. Instructions on how to install SPM are available in the [SPM Online Documentation.](https://www.fil.ion.ucl.ac.uk/spm/docs/installation/)

1. Download `spm12.zip` from the [SPM website](https://www.fil.ion.ucl.ac.uk/spm/software/download/).
2. Unzip `spm12.zip` into a folder of your choice, such as `C:\Users\<login>\Documents\MATLAB\spm12`.
3. Start MATLAB and add SPM to your path using the following MATLAB command:


```matlab
addpath('C:\Users\<login>\Documents\MATLAB\spm12')
savepath % if you want to save the current MATLAB path
```

### Access Batch Script Files

For this tutorial, all necessary code is available on GitHub in the [matlab-spm-scripts-jsh repository](https://github.com/smwong4/matlab-spm-scripts-jsh-modified). You have two options to access these files: download them directly to your local machine or use Git source control within MATLAB.

#### Option 1: Clone the Git Repository (Recommended)

Using MATLAB's Current Folder browser, you can clone an existing remote repository, add files to your local repository, commit changes, and push or pull changes to and from the remote repository. Even if you don’t plan on modifying these scripts, using Git with MATLAB is good practice.

*First, if you haven't already set up Git source control in MATLAB, follow these steps:*

1. Ensure Git is installed on your system. You can download it from [git-scm.com](https://git-scm.com/).
2. In MATLAB, go to the **Home** tab.
3. Click on **Environment** and then **Preferences**.
4. In the **Preferences** dialog, select **MATLAB > General > Source Control**.
5. Choose **Enable MathWorks source control integration**.


*To clone the [matlab-spm-scripts-jsh repository](https://github.com/smwong4/matlab-spm-scripts-jsh-modified), follow these steps:*

1. In the MATLAB Current Folder browser, right-click on the white space and select **Source Control > Manage Files**. MATLAB will open the **Manage Files Using Source Control** dialog box.
2. Set the **Source control integration** option to **Git**.
3. Click the **Change** button next to the **Repository path** field. This will open the **Select a Repository** dialog box.
4. Enter the URL of the repository you want to clone: `https://github.com/smwong4/matlab-spm-scripts-jsh-modified`.
5. Click the **Validate** button to check the remote repository path.
6. In the **Sandbox** field, enter the path of the working folder where you want to store the retrieved files. The folder must be empty. For this tutorial, you can create a new folder called `neuronest-matlab-tutorial`. Enter the desired path, e.g., `C:\Users\<login>\Documents\MATLAB\neuronest-matlab-tutorial`, into the **Sandbox** field.
7. Click the **Retrieve** button. If prompted, confirm the creation of the new folder.
8. After cloning the repository, you can change the path to the remote repository if needed by right-clicking in the working folder, selecting **Source Control > Remote**, and specifying the new path.

<img width="629" alt="image" src="https://github.com/user-attachments/assets/0d12846f-28c5-495c-a542-bbbd0b718e82">


#### Option 2: Download All Files Locally

Alternatively, you can download all the files and create a folder named `neuronest-matlab-tutorial` to store them. You will need to add this folder to your MATLAB path. If the folder is already within your MATLAB directory, you can refer to the files by name rather than using the absolute path.

```matlab
addpath('neuronest-matlab-tutorial')
savepath % if you want to save the current MATLAB path
```





### Open the Main Script File: spm_batchScriptingExample_jsh
Once you have all the script files in your MATLAB folder, identify the main script file, `spm_batchScriptingExample_jsh.m`. This file serves as the pipeline, sequentially calling all the necessary steps, which include:

1. **Initializing the data**: Pointing the script to the correct fMRI timeseries data.
2. **Preprocessing the data**: This includes steps such as realignment, smoothing, and segmentation, handled by `spm_standardPreproc_jsh`.
3. **Creating the first-level statistical design**: Analyzing the preprocessed data with `spm_specify1stlevel_jsh`.
4. **Running the group-level analysis**:
   - Estimating the model fit with `spm_estimateModel_jsh`.
   - Creating the task contrast for statistical testing with `spm_setupTaskContrast_jsh`.
   - Running and displaying the results with `spm_runResults_jsh`, which generates a 3D map of thresholded t-values indicating task-related brain activity.

This tutorial page includes code that can be copied into your MATLAB command line for each step, but it is recommended that you open the main script directly and run each chunk as you follow the tutorial steps instead.



## Step 1: Import and Initialize Data Files

### Download OpenNeuro Dataset

Find the ["ds000157"](https://openneuro.org/datasets/ds000157/versions/00001) dataset on OpenNeuro. This dataset includes NIfTI files for each subject’s functional and anatomical MRI scans, organized in [BIDS format](bids_data.html).

<img width="600" alt="image" src="https://github.com/user-attachments/assets/42300427-c8c2-488c-83b1-49190113f1c0">


You need to download the *entire dataset* using the provided options, either directly with your browser or using DataLad.

#### Option 1: Browser

  <img width="600" alt="image" src="https://github.com/user-attachments/assets/70f82229-58cf-4c32-a9b6-d3c91f724046">
  
If you download the data directly with your browser, ensure that the files are unzipped correctly in a folder named `ds000157` and are properly organized within the MATLAB folder structure.

#### Option 2: DataLad

<img width="773" alt="image" src="https://github.com/user-attachments/assets/4e841224-520b-4313-8d1d-68ef6658321f">

If you do not already have [DataLad](datalad_data.html) installed, you will need to install it using your terminal. Download the dataset using DataLad and navigate to the dataset directory. You will then download the dataset contents recursively.


```bash
# Install datalad
pip install datalad

# Download the dataset
datalad install https://github.com/OpenNeuroDatasets/ds000157.git
cd ds000157
datalad get -r .
```

For more detailed instructions on using DataLad to download OpenNeuro datasets, refer to the [DataLad Handbook](https://handbook.datalad.org/en/latest/usecases/openneuro.html).

### Add the Dataset to MATLAB's Search Path

Once the dataset is downloaded, ensure all the files are in a folder named `ds000157`. Add this folder to your MATLAB path. By adding the folder to the path, you ensure that MATLAB can access all the necessary data files without needing to specify the full directory paths each time.

```matlab
% Add data to MATLAB search path
addpath('ds000157')
savepath % if you want to save the current MATLAB path
```

### Initialize File Locations and Other Variables

Before running the preprocessing, ensure that the data is unzipped and the necessary file paths are set. The script you will run takes care of these steps automatically, including checking that the data files were downloaded and extracted properly and that MATLAB can access them before moving onto the next step.

```matlab

disp('CONFIGURING PATHS AND PARAMETERS')

% Configure paths for dataset, SPM, and git repository
% Example of using absolute path if the directory is not already in MATLAB path:
% spm_dir = '/Users/candylab/Documents/MATLAB/spm12' 
spm_dir = 'spm12'  % Path to SPM.
data_dir = ''ds000157';  % Path to data. 
git_dir = 'neuronest-matlab-tutorial';  % Path to github repository
addpath(spm_dir);
addpath(data_dir);
addpath(git_dir);

% Configure parameters
subj = 'sub-01';                                         % Subject ID. Can be changed to any subject id in data set
fwhm = 6;                                                % Smoothing kernel (mm)

% Unzip nifty files
gunzip([data_dir filesep subj filesep 'anat' filesep subj '_T1w.nii.gz']); 
gunzip([data_dir filesep subj filesep 'func' filesep subj '_task-passiveimageviewing_bold.nii.gz'])

% Creating elements for file locations
s_fn = [data_dir filesep subj filesep 'anat' filesep subj '_T1w.nii'];
f_fn = [data_dir filesep subj filesep 'func' filesep subj '_task-passiveimageviewing_bold.nii'];
stats_dir = [data_dir filesep subj filesep 'stats'];

% Create stats directory if it doesn't exist
if ~exist(stats_dir,'dir')
    mkdir(stats_dir)
end

disp('CHECKING FOR FILES')

% Check for the anatomical image file
if exist(s_fn, 'file')
    fprintf('Anatomical image file exists: %s\n', s_fn);
else
    error('Anatomical image file not found: %s\n', s_fn);
end

% Check for the functional image file
if exist(f_fn, 'file')
    fprintf('Functional image file exists: %s\n', f_fn);
else
    error('Functional image file not found: %s\n', f_fn);
end

% Check file sizes (optional)
anat_info = dir(s_fn);
func_info = dir(f_fn);
fprintf('Anatomical image file size: %d bytes\n', anat_info.bytes);
fprintf('Functional image file size: %d bytes\n', func_info.bytes);

disp('Files are all set!')

```

## Step 2: Run Preprocessing Scripts

The preprocessing pipeline includes several critical steps: slice-time correction, motion correction, coregistration, normalization, and smoothing. These processes ensure that the fMRI data is aligned, normalized, and prepared for statistical analysis.

The preprocessing script will check if these steps have already been completed. If the data has already been processed, the script will skip the redundant steps. Otherwise, it will proceed with preprocessing the structural and functional images, ensuring that they are ready for subsequent analysis.

```matlab
%% PREPROCESSING
disp('PREPROCESSING')

% Preprocess structural and functional images (if not already)
[d, f, e] = fileparts(s_fn);
[d1, f1, e1] = fileparts(f_fn);

if exist([d filesep 'rc1' f e], 'file')
    disp('...preproc already done, saving variables...')
    preproc_data = struct;
    % Structural filenames
    preproc_data.forward_transformation = [d filesep 'y_' f e];
    preproc_data.inverse_transformation = [d filesep 'iy_' f e];
    preproc_data.gm_fn = [d filesep 'c1' f e];
    preproc_data.wm_fn = [d filesep 'c2' f e];
    preproc_data.csf_fn = [d filesep 'c3' f e];
    preproc_data.bone_fn = [d filesep 'c4' f e];
    preproc_data.soft_fn = [d filesep 'c5' f e];
    preproc_data.air_fn = [d filesep 'c6' f e];
    preproc_data.rstructural_fn = [d filesep 'r' f e];
    preproc_data.rgm_fn = [d filesep 'rc1' f e];
    preproc_data.rwm_fn = [d filesep 'rc2' f e];
    preproc_data.rcsf_fn = [d filesep 'rc3' f e];
    preproc_data.rbone_fn = [d filesep 'rc4' f e];
    preproc_data.rsoft_fn = [d filesep 'rc5' f e];
    preproc_data.rair_fn = [d filesep 'rc6' f e];
    % Functional filenames
    preproc_data.rfunctional_fn = [d1 filesep 'r' f1 e1];
    preproc_data.srfunctional_fn = [d1 filesep 'sr' f1 e1];
    preproc_data.mp_fn = [d1 filesep 'rp_' f1 '.txt'];
    preproc_data.MP = load(preproc_data.mp_fn);
else
    disp('...running preprocessing batch jobs...')
    preproc_data = spm_standardPreproc_jsh(f_fn, s_fn, fwhm, spm_dir);
end

% Check coregistration and segmentation
spm_check_registration(s_fn, [preproc_data.rfunctional_fn ',1'], preproc_data.rgm_fn, preproc_data.rwm_fn, preproc_data.rcsf_fn)
disp('Preprocessing done!')
```

## Step 3: Run a First-Level Analysis Batch Script

The first-level analysis script sets up the statistical design parameters based on the task data. It then processes the preprocessed data to create a model of brain activity during the task. This model will be used to identify which brain regions are activated by the task.

The script will display and allow you to explore the design matrix, providing insights into the experimental design and the structure of the data.

```matlab
disp('SETTING UP 1ST LEVEL STATS DESIGN');

% Set up statistical design parameters, based on task data
sess_params = struct;
sess_params.timing_units = 'secs';
sess_params.timing_RT = 1.6;
sess_params.cond_name = 'Pictures';
sess_params.cond_onset = [0; 40.1; 77.2; 111.3; 143.3; 179.4; 218.5; 251.5; 299.6; 334.7; 374.8; 411.9; 445.9; 478.0; 514.1; 553.2];
sess_params.cond_duration = [24.1000; 24.06; 24.07; 24.06; 24.06; 24.07; 24.04; 24.06; 24.07; 24.10; 24.06; 24.06; 24.09; 24.09; 24.06; 24.07];

% Call script to set up design
spm_specify1stlevel_jsh(stats_dir, preproc_data.srfunctional_fn, preproc_data.mp_fn, sess_params);

% Display/explore design matrix 
load([stats_dir filesep 'SPM.mat']);
spm_DesRep('fMRIDesMtx', SPM, 1, 1);

disp('1st level stats done!')

```

## Step 4: Run a Group-Level Analysis Batch Script

### Estimate Model

The model estimation process involves running a general linear model (GLM) on the first-level data to estimate the brain's response to the task. This step is crucial for identifying significant brain activity patterns across the subject's data.

```matlab
disp('ESTIMATING MODEL');

spm_estimateModel_jsh(stats_dir);

disp('Model estimation done!')
````


### Set Up Task Contrast

Task contrasts are used to compare different conditions within the experimental design. This script sets up the necessary contrasts to test hypotheses about brain activity during the task. The contrast is then applied to the model to generate statistical maps that highlight task-related brain regions.

```matlab
disp('SETTING UP TASK CONTRAST');

[Ntt, Nregr] = size(SPM.xX.X);
contrast_params = struct;
contrast_params.weights = zeros(1, Nregr); 
contrast_params.weights(1) = 1;
contrast_params.name = 'Picture viewing';
spm_setupTaskContrast_jsh(stats_dir, contrast_params);

disp('Task contrast set up done!')
````

### Run Results

Finally, the results script runs the contrasts and displays the thresholded statistical maps. These maps indicate which brain areas are likely to be involved in the task based on the fMRI data. After completing this step, you will have a full analysis of the fMRI dataset, from preprocessing to results visualization.

```matlab
disp('RUNNING RESULTS');

spm_runResults_jsh(stats_dir)

disp('Results displayed! Good job on making it through the tutorial!')
````

## Conclusion

By following this tutorial, you have learned how to set up and execute a complete fMRI data analysis pipeline in MATLAB using SPM12. This process involved downloading and preparing the data, running preprocessing steps, performing first-level analysis to model individual subject data, and conducting group-level analysis to draw broader conclusions about brain activity. Mastery of these techniques allows for efficient and reproducible fMRI data analysis, which is essential for advancing research in psychology and neuroscience.



## Resources and References

- [SPM12 Documentation](https://www.fil.ion.ucl.ac.uk/spm/doc/)
- [SPM12 Manual - Auditory Data Example](https://www.fil.ion.ucl.ac.uk/spm/doc/spm12_manual.pdf#Chap:data:auditory)
- [OpenNeuro](https://openneuro.org/)
- [Andy's Brain Blog: Running SPM First-Level Analyses from Batch Scripts](https://andysbrainblog.blogspot.com/2014/06/running-spm-first-level-analyses-from.html)
- [SPM MATLAB Scripting Tutorials by Janina Sheunis](https://jsheunis.github.io/2018-06-28-spm12-matlab-scripting-tutorial-1/)
  - [Tutorial 1: Introduction to MATLAB and SPM Scripting](https://jsheunis.github.io/2018-06-28-spm12-matlab-scripting-tutorial-1/)
  - [Tutorial 2: Batch Processing with SPM and MATLAB](https://jsheunis.github.io/2018-06-28-spm12-matlab-scripting-tutorial-2/)
  - [Tutorial 3: Advanced Scripting Techniques](https://jsheunis.github.io/2018-06-28-spm12-matlab-scripting-tutorial-3/)
- [GitHub Repository: SPM fMRI Example Pipeline by Phil Dean](https://github.com/phildean/SPM_fMRI_Example_Pipeline/tree/master)
- [Batch Processing in SPM](https://myguide.bagarinao.com/batch-processing-in-spm/)
- [SPM Programming Intro on Wikibooks](https://en.wikibooks.org/wiki/SPM/Programming_intro)
- [Essentials of Neuroscience with MATLAB](https://github.com/mikexcohen/EssentialsOfNeuroscienceWithMATLAB/tree/main/module4_FMRI)
- [SPM Datasets and Tutorials](https://www.fil.ion.ucl.ac.uk/spm/data/)
  - [Face Representation Dataset](https://www.fil.ion.ucl.ac.uk/spm/data/face_rep/)
  - [Auditory Dataset](https://www.fil.ion.ucl.ac.uk/spm/data/auditory/)
  - [Attention Dataset](https://www.fil.ion.ucl.ac.uk/spm/data/attention/)
  - [Face RFX Dataset](https://www.fil.ion.ucl.ac.uk/spm/data/face_rfx/)
  - [DCM BMS Dataset](https://www.fil.ion.ucl.ac.uk/spm/data/dcm_bms/)
- [Principles of fMRI Analysis - Rik Henson](https://imaging.mrc-cbu.cam.ac.uk/imaging/AnalysisPrinciples)
- [SPM fMRI Analysis - Visualization of Results](https://www.bobspunt.com/resources/teaching/group-analysis/#:~:text=Visualization%20of%20Results%20using%20bspmview,fMRI%20results%20estimated%20in%20SPM.)
- [SPM and MATLAB Functions - Christophe Pernet](https://github.com/CPernet)
  - [SPM Real-Time](https://github.com/CPernet/spmrt)
  - [PiLab](https://github.com/CPernet/pilab)
  - [Various MATLAB Functions](https://github.com/CPernet/various_matlab_functions)
  - [SPMPC](https://github.com/CPernet/SPMPC)
- [Essentials of Neuroscience with MATLAB on MATLAB Central](https://www.mathworks.com/matlabcentral/fileexchange/154381-essentials-of-neuroscience-with-matlab?s_tid=srchtitle)
- [SPM Cheat Sheets and Tutorials on Wikibooks](https://en.wikibooks.org/wiki/SPM/How-to)
- [SPM and Nibabel Usage Guide](https://nipy.org/nibabel/devel/spm_use.html)
