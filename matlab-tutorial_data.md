# fMRI Data Analysis in MATLAB using 

This tutorial guides you through the process of analyzing fMRI data using MATLAB and SPM (Statistical Parametric Mapping). The focus is on scripting and using MATLAB commands rather than the SPM GUI. We will use a dataset from OpenNeuro and process it using pre-written batch scripts. *All necessary code is available on the **matlab-spm-scripts-jsh** repository.*

The goal here is to use Matlab and SPM12 batch scripting to run automated pipelines that preprocess and analyze task-based fMRI data with minimal user input, using steps that one would typically have completed through the GUI (e.g. Realign, Smooth, Segment, Specify 1st-level, Estimate or Results, as indicated below).


## Prerequisites

To be able to follow this tutorial, you will have to have [SPM12](https://www.fil.ion.ucl.ac.uk/spm/software/download/) installed and add on your path. Instructions on how to install SPM are available in the [SPM Online Documentation.](https://www.fil.ion.ucl.ac.uk/spm/docs/installation/) 

1. Download `spm12.zip` from the [SPM website](https://www.fil.ion.ucl.ac.uk/spm/software/download/)

2. Unzip `spm12`.zip in a folder of your choice, such as `C:\Users\login\Documents\MATLAB\spm12`.

3. Start MATLAB and add SPM to your path using the following MATLAB prompt:

```matlab
addpath('C:\Users\<login>\Documents\MATLAB\spm12')
savepath % if you want to save the current MATLAB path
```

## Step 1: Import and Initialize Data and Script Files 

### Access Script Files

For this tutorial, all necessary code is available on GitHub in the [matlab-spm-scripts-jsh repository](https://github.com/smwong4/matlab-spm-scripts-jsh-modified). To access these files, you have two options: you can either download the files directly to your local machine and add them to your MATLAB path, or you can use Git source control within MATLAB. 

If you prefer to download the files locally, you can skip this step.

```matlab
addpath('C:\Users\<login>\Documents\MATLAB\spm12')
savepath % if you want to save the current MATLAB path
```

*Option 1: Clone the  Git Repository (Recommended)*

With MATLAB's Current Folder browser, you can clone an existing remote repository, add files to your local repository, commit changes, and push or pull changes to and from the remote repository. Even though you may not be making changes to these scripts using Git with MATLAB is good practice.

If you haven't already set up Git source control in MATLAB, follow these steps:

1. Ensure Git is installed on your system. You can download it from [git-scm.com](https://git-scm.com/).
2. In MATLAB, go to the **Home** tab.
3. Click on **Environment** and then **Preferences**.
4. In the **Preferences** dialog, select **MATLAB > General > Source Control**.
5. Choose **Enable MathWorks source control integration**.


To clone the [matlab-spm-scripts-jsh repository](https://github.com/smwong4/matlab-spm-scripts-jsh-modified), follow these steps:

1. In the MATLAB Current Folder browser, right-click on the white space and select **Source Control > Manage Files**. MATLAB will open the **Manage Files Using Source Control** dialog box.
2. Set the **Source control integration** option to **Git**.
3. Click the **Change** button next to the **Repository path** field. This will open the **Select a Repository** dialog box.
4. Enter the URL of the repository you want to clone: `https://github.com/smwong4/matlab-spm-scripts-jsh-modified`.
5. Click the **Validate** button to check the remote repository path.
6. In the **Sandbox** field, enter the path of the working folder where you want to store the retrieved files. The folder must be empty. For this tutorial, you can create a new folder called `neuronest-matlab-tutorial`. Enter the desired path, e.g., `C:\Users\<login>\Documents\MATLAB\neuronest-matlab-tutorial`, into the **Sandbox** field.
7. Click the **Retrieve** button. If prompted, confirm the creation of the new folder.
8. After cloning the repository, you can change the path to the remote repository if needed by right-clicking in the working folder, selecting **Source Control > Remote**, and specifying the new path.

<img width="629" alt="image" src="https://github.com/user-attachments/assets/0d12846f-28c5-495c-a542-bbbd0b718e82">



*Option 2: Download all files locally*

Download all the files and create a folder named `neuronest-matlab-tutorial` to store them. Add this folder to your MATLAB path by running the following code. If the `neuronest-matlab-tutorial` folder is within your MATLAB directory on your local computer already, you can refer to the files by name rather than using the absolute path.

```matlab
addpath('neuronest-matlab-tutorial')
savepath % if you want to save the current MATLAB path
```

### Download OpenNeuro Dataset
Find the ["ds000157"](https://openneuro.org/datasets/ds000157/versions/00001) data set on OpenNeuro. You will see in each subject's file that there are nifty files for their functional and anatomical MRI. These files are organized in [BIDS format](bids_data.html)

<img width="756" alt="image" src="https://github.com/user-attachments/assets/42300427-c8c2-488c-83b1-49190113f1c0">


You need to download the *entire dataset* using the provided options, such as directly downloading with your browser or using datalad.

*Option 1: Browser*
If you download the data directly with your browser, you will want to be sure you 
  <img width="772" alt="image" src="https://github.com/user-attachments/assets/70f82229-58cf-4c32-a9b6-d3c91f724046">


*Option 2: Datalad*

If you do not have it already, you will need to install Datalad using your terminal.  

Download the dataset using datalad and navigate to the dataset directory. You will then download the dataset contents recursively.

```bash
# Install datalad
pip install datalad

# Download the dataset
datalad install https://github.com/OpenNeuroDatasets/ds000157.git
cd ds000114
datalad get -r .
```

<img width="773" alt="image" src="https://github.com/user-attachments/assets/4e841224-520b-4313-8d1d-68ef6658321f">

You can learn more about downloading datasets with DataLad [here](https://handbook.datalad.org/en/latest/usecases/openneuro.html).

If you want a general overview on what DataLad is, you can visit [here](datalad_data.html).


### Import Data into MATLAB

You will then add the dataset directory to MATLAB's search path. As long as the dataset is in the MATLAB folder on your computer and you are in the MATLAB search path on in MATLAB, you should be able to add the dataset by simply indicating the name of the file. 

Make sure all the files are in a folder named `ds000157`. Add this folder to your MATLAB path by running the following code. If the `ds000157` folder is within your MATLAB directory on your local computer already, you can refer to the files by name rather than using the absolute path.


```matlab
%Add data to Matlab search path
addpath('ds000157')
savepath % if you want to save the current MATLAB path
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
