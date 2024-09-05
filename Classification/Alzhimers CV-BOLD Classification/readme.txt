Installation
________________________________________
Dependencies
Python(>=3.5)
Keras==2.2.4
nilearn==0.5.2
scipy==1.2.1
nibabel==2.4.1
numpy==1.16.2
imbalanced_learn==0.5.0
imblearn==0.0
scikit_learn==0.21.2
densratio==0.2.2
skimage==0.0
matplotlib==3.0.3
Download all using:
pip3 install -r requirements.txt
________________________________________
Model
Coefficient of variation over time for BOLD signal was used as the input data for the model. The model Consists of three main steps:
Loading and preprocessing the input data
Voxel Selection using cross validation for creating mask of most effective voxels
Classify the masked data using many classifiers and printing the results (Gaussian process classifier provides the best performance in high dimensional space.
________________________________________
Running the code
python3 main.py
Change input parameters and variables in the main.py file to fit your requirements and preferences The default script runs under 10 minutes on an average laptop using under 1 GB of memory.
________________________________________
Results
The results folder sould be created by you and give it name to the variable 'Results_directory' , it contains the measured performace in Results.txt, the used parameters and chosed classifier README.txt, mask of effective voxels, and voxel importance weight. The provided pretrained model in Output_results_directory gives the following confidence level:
	Median	Min(.95 CL)	Max(.95 CL)
Accuracy	.702	.555	.835
F1_score	.723	.595	.841
AUC	.781	.721	.856

	
Note the mask and weights files images are in NIFTI format, you can use FSL utils or nibabel library to process the data or FSLeyes to visualize.
