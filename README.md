# Semi-Supervised Medical Fraud Detection Using Autoencoders
### By: Rayhaan Rasheed
  The George Washington University
  
  https://zenodo.org/record/3565570#.XepR9ZNKjVo
  
  https://rrasheed.github.io/cmsfrauddetection/
  
## Abstract
<break>
Every day, patients seek medical counsel and assistance from physicians, but access to affordable healthcare is still a pressing issue. For those who qualify, the United States government provides financial support in the form of its Medicare and Medicaid programs. These programs allow citizens to receive quality care, and physicians are paid from the government's pocket. Since physicians are not billing the patient directly, some have resorted to committing fraud to get more money. Large abnormalities can easily be detected, but many fraudulent physicians are difficult to detect since they could identically resemble normal physicians. Leveraging publically available data, anomaly detection systems can be developed to point out fraudulent physicians while working under a highly imbalanced class setting. With only 0.017% as the fraudulent class size, a deep anomaly detection system is developed to understand the minute differences between the two classes and gain a good understanding of the overall feature space. The model of choice is an Autoencoder since it is commonly used for anomaly detection problems due to its ability to understand the fundamental components of the input data and be able to reconstruct the data using these components. Three versions that differed in the number of hidden layers were compared to find the best network architecture for detecting fraudulent physicians. The shallow network, which only contained one hidden layer between the input and output layers, was the best model because it detected the most fraudulent cases maintaining the least number of false negatives.

## Data
<break>
CMS released large, multidimensional datasets for the different parts of their Medicare/Medicaid program. For this experiment, only the Provider Utilization and Payment Data (Part B) is used to understand and detect healthcare fraud. Part B helps cover doctors' services and outpatient care. This is where a high percentage of fraud exists since overbilling is one of the most common forms of fraudulent activities. Each observation in the dataset corresponds to a procedure performed by a specific physician, where each physician is given a unique NPI code.
To know which physicians and organizations are fraudulent, the Department of Health and Human Services' Office of the Inspector General (OIG) established the List of Excluded Individuals and Entities (LEIE), which is maintained monthly. The OIG is required by law to exclude anyone from federally funded healthcare programs if they are convicted of Medicare/Medicaid fraud. [​ 4]​ The LEIE is a dataset where each person has a set of features including their unique NPI code.

## Network Architecture
<break>
There are three Autoencoders that are tested and compared to one another, and aside from the depth of the network (i.e. number of hidden layers), the three models all have a training batch of 1,000 observations, equal input and output shapes, a hyperbolic tangent activation function in between each layer, and the same hyperparameters. By making the numbers of hidden layers vary, we can test for the optimal depth that fully understands the Part B data. The first model is a shallow Autoencoder (98-12-98) with one hidden layer in between the input and output layers. The second model (98-35-12-35-98) has three hidden layers – the bottleneck, one for the encoder, and one for the decoder. Lastly, the third model (98-48-24-12-24-48-98) contains five hidden layers.
