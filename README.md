
# Machine Learning Engineer Capstone: Starbucks Offer Conversion

## Overview

### Domain Background:
Direct-to-consumer marketing is important to brands and is very valuable. It allows companies to build a relationship with customers that fosters greater retention and loyalty. Leveraging in-app messaging has several benefits. For one, it’s generally cheaper to retain existing customers than it is to acquire new customers. Mobile app adoption and in-app commerce enables companies to leverage data to better understand user preferences. This creates an opportunity (and challenge) to personalize offers and marketing content for a given customer. All customers have different preferences and tastes. They also have different price elasticities and spending habits. Understanding which customers will be most receptive to a given offer represents a nuanced, yet important business challenge.

### Problem Statement:
Given that we know different users will respond differently to different offers, our task is to determine how likely a given user that receives an offer will convert based on information about the user and the offer itself. By ‘convert’, we mean the user takes advantage of the offer by meeting the requirements of the transaction. In practice, this model could be used to determine which offers should be given to particular users based on their likelihood of converting . We can also evaluate the which offers are users overall my responsive to, and what drivers (i.e. user demographics and offer metadata) are most correlated with conversion. This type of key driver analysis can offer some important insights to marketing teams on how to both tailor offers and target customers for future promotions.


## Reproducing the Project

### Step 1) Create a Sagemaker Notebook Instance
First, start by logging in to the AWS console, opening the SageMaker dashboard, selecting Notebook Instances and clicking on Create notebook instance.

You may choose any name you would like for your notebook. Choose ml.t2.medium instance, as this is covered under the free tier.

Next, under IAM role select Create a new role. You should get a pop-up window that looks like the one below. The only change that needs to be made is to select None under S3 buckets you specify

Now scroll down and click on Create notebook instance.

Once your notebook instance has started and is accessible, click on open to get to the Jupyter notebook main page.

Reference: [Creating a Notebook Instance](https://docs.aws.amazon.com/sagemaker/latest/dg/howitworks-create-ws.html)

### Step 2) Setup Notebook Instance Directory Structure

-- README

-- notebooks

    -- 1_data_exploration_cleaning.ipynb
    -- 2_eda.ipynb
    -- 3_data_preprocessing.ipynb
    -- 4_linear_learner_initial_model_1.ipynb
    -- 5_linear_learner_hp_tuning_model_2.ipynb
    -- 6_xgboost_model_3.ipynb
    -- 7_post_hoc_analysis.ipynb

-- input

    -- profile.json
    -- portfolio.json
    --transcript.json
    
Note: Subsequent data objects are included in the input folder for convenience and can be read locally, but the analysis can replicated with notebooks and the 3 raw json files only (profile.json, portfolio.json, and transcript.json.

### Step 3) Run the Notebooks
The analysis flows in the following notebook order:
1. 1_data_exploration_cleaning.ipynb
2. 2_eda.ipynb
3. 3_data_preprocessing.ipynb
4. 4_linear_learner_initial_model_1.ipynb
5. 5_linear_learner_hp_tuning_model_2.ipynb
6. 6_xgboost_model_3.ipynb
7. 7_post_hoc_analysis.ipynb

In order to run the modeling/analysis files (notebooks 4-7) the 1_data_exploration_cleaning.ipynb and 2_data_preprocessing.ipynb notebooks must be both run to completion (in order). These notebooks contain all data cleaning/ preparation steps that transform the raw data into the appropriate model inputs. Once run, noteboooks 4-6 do not have to be run in succession, and can be run independently. However, the xgboost_model_3.ipynb notebook must ran in order for the appropriate data inputs to be available for 7_post_hoc_analysis.ipynb.

### Library Documentation
[Pandas](https://pandas.pydata.org/docs/)
[NumPy](https://numpy.org/doc/)
[scikit-learn](https://scikit-learn.org/stable/)
[Seaborn](https://seaborn.pydata.org/)
[matplotlib](https://matplotlib.org/stable/contents.html)
[sagemaker](https://sagemaker.readthedocs.io/en/stable/)
[boto3](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html)
[os](https://docs.python.org/3/library/os.html)
[time](https://docs.python.org/3/library/time.html)
[urllib](https://docs.python.org/3/library/urllib.html)
[json](https://docs.python.org/3/library/json.html)
[math](https://docs.python.org/3/library/math.html)

### Other Resources
[SageMaker Developer Guide](https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html)

[Linear Leaner Algorithm](https://docs.aws.amazon.com/sagemaker/latest/dg/linear-learner.html)

[XGBoost Algorithm](https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost.html)

[SageMaker Notebook Examples](https://github.com/aws/amazon-sagemaker-examples)

### Notes
Please note that the project workflow utilizes AWS S3 for intermediate storage of data objects created within each notebook as well as model training and analysis