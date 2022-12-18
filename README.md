# MachineLearningOmega
Team-project of the machine learning lecture in the Fall Semester 22' at Ewha. Team Omega 

## Dataset
The original dataset is available at https://www.kaggle.com/code/hainescity/company-s-ideal-customers


The final dataset is "finalDataSet.csv", which is already preproccessed.
- With "datasetPreprocessing.ipynb" preprocessing has been applied to the original data

## Oversampled Dataset
The oversampled data set is split into the train set "train_oversampled.csv" and the test set "test_set.csv"
- With "ApplyOversampling.ipynb" oversampling has been applied to the finalDataSet.csv

## Using AzureML to find the best model

1. Register an account with Microsoft Azure. (Azure for Students gives free Credits/Services for students)
2. Create a workspace:
   1. Choose a name.
   2. Use the suggested subscription and resource group.
   3. Select a region near you.
3. Under the big '+' select *Data asset*. (Repeat for test_set.csv)
   1. Choose a name and select *Tabular* for Type. Press *Next*
   2. Choose *From local files*. Press *Create*.
   3. Use the pre-selected settings under "Storage type" and continue.
   4. Use the blue *Upload*-Button and select the "train_oversampled.csv".
   5. Use the pre-selected settings and continue.
   6. Check if the data-type is correct and continue.
   7. Review the settings and *Create*.
4. Back to the Big '+' and select *Compute instance*.
   1. Choose a name for the compute instance.
   2. Choose a suitable VM-size.
5. Select the *Automated ML*.
   1. Press *New automated ML job*.
   2. Select your data asset.
   3. Enter a experiment name.
   4. Choose 'Succesful_cmp' for *Target column*.
   5. Select "compute instance" as *Select compute type*.
   6. Select your previous created instance. And continue.
   7. Select *Classification* and continue.
   8. Select "train-validation split" for *Validation type*. Choose 15%
   9. For *Test data assest* select "Provide a test data assest" and choose the "test_set".
   10. Press finish.
6. View best model and metrics/hyperparameters.
    1. Go back to "Automated ML"-tab.
    2. Select your Job under "Recent Automated ML jobs".
    3. On the right side you can open *view all other metrics* for the best model.
   4. You can view all Models under *Models*.

## Using the best model (outside of AzureML)
Please Follow these steps to reach the results:

1. Open Models.ipynb with IDE

2. Adjust file path in for three data: (finalalDataSet.csv, test_set, tain_oversampled)

3. Run all code cell to see the results. 

*The code was written in python. We recommend using python 3.10 for the correct functioning of the code. We also recommend using the PyCharm integrated development environment (IDE), as the code has been developed in this IDE.
