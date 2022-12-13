# Credit_Risk_Analysis

## Overview
In this analysis we will help Lending Club, a peer-to-peer lending services company, to forecast credit risk using machine learning. We will use oversamping, undersampling, and combination techniques to determine which model will perform best on this dataset. 
## Resources

* conda 22.11.1
* python 3.7.15
* jupyter notebook 7.4.7
* scikit-learn 1.0.2
* imbalanced-learn 0.10.0

## Results

  
  ### RandomOverSampler
  * Object to over-sample the minority class(es) by picking samples at random with replacement.
  
  ![image](https://user-images.githubusercontent.com/110706169/207197165-b615d980-d1f5-4bcf-9591-535ab8f47c8b.png)
  
  ![image](https://user-images.githubusercontent.com/110706169/207197319-f665430a-edae-45d6-8fd7-c8f7f1bdb8b7.png)
  * The **balance_accuracy_score** is: 62%
  
  ![image](https://user-images.githubusercontent.com/110706169/207206234-52d740e5-3a53-430c-b8da-369a7a03a51a.png)
 
  <kbd>![image](https://user-images.githubusercontent.com/110706169/207430660-4209525a-bf11-442e-80a5-9da03e3af620.png)</kbd>
  
  
  * Precision High Risk: 1%
  * Precision Low Risk: 100%
  * Recall High Risk: 60%
  * Recall Low Risk: 65%
   
   ### SMOTE(Synthetic Minority Oversampling Technique)
   
   ![image](https://user-images.githubusercontent.com/110706169/207206352-3905ccc7-9143-4b5a-b2f0-4b4177bf4299.png)

   ![image](https://user-images.githubusercontent.com/110706169/207206417-71a94c70-4414-4515-a1d8-052a355dda98.png)
    
  * The **balance_accuracy_score** is: 65%
      
   ![image](https://user-images.githubusercontent.com/110706169/207206510-1c0ccd0d-6603-4d50-a81b-bb32dec55564.png)
  
   <kbd>![image](https://user-images.githubusercontent.com/110706169/207430708-9438c597-315e-43ac-9acb-520dd1a49b49.png)</kbd>

  * Precision High Risk: 1%
  * Precision Low Risk: 100%
  * Recall High Risk: 64%
  * Recall Low Risk: 66%
  
  
   ### ClusterCentroids
   
   * Method that under samples the majority class by replacing a cluster of majority samples by the cluster centroid of a KMeans algorithm.
   
   ![image](https://user-images.githubusercontent.com/110706169/207206555-cb1b1543-b744-41bf-b857-5a75354d1ce2.png)
  
   ![image](https://user-images.githubusercontent.com/110706169/207206587-b541c6ff-0924-4a53-a02b-a36f15c034c0.png)
   
   * The **balance_accuracy_score** is: 51%
    
   ![image](https://user-images.githubusercontent.com/110706169/207206618-afb4b29a-ce64-4384-8b61-5cab44da3a69.png)

   <kbd>![image](https://user-images.githubusercontent.com/110706169/207430995-148a5fb4-7267-42e6-be75-56861e1cecbf.png)</kbd>
   
   * Precision High Risk: 1%
  * Precision Low Risk: 100%
  * Recall High Risk: 60%
  * Recall Low Risk: 43%
  
   ### SMOTEENN(SMOTE + Edit Nearest Neighbor)
   
   * Combine over- and under-sampling using SMOTE and Edited Nearest Neighbours.
   
   ![image](https://user-images.githubusercontent.com/110706169/207206833-f682fa40-fb04-4170-b25b-0a0b750a57b3.png)
  
   ![image](https://user-images.githubusercontent.com/110706169/207206868-31202972-d043-4042-97ec-262b959123d2.png)
  
   * The **balance_accuracy_score** is: 65%
      
   ![image](https://user-images.githubusercontent.com/110706169/207206890-1b73e0ff-3b8d-4018-ae75-10ef6f41b130.png)

   <kbd>![image](https://user-images.githubusercontent.com/110706169/207431047-45435190-7033-41ed-a1bb-b18a2064223f.png)</kbd>
   
  * Precision High Risk: 1%
  * Precision Low Risk: 100%
  * Recall High Risk: 72%
  * Recall Low Risk: 58%
  
   ### BalancedRandomForestClassifier 
   
   * A balanced random forest randomly under-samples each boostrap sample to balance it.
   
   ![image](https://user-images.githubusercontent.com/110706169/207207091-0e752f7f-a8b2-49cc-8497-160a2492af93.png)
  
   ![image](https://user-images.githubusercontent.com/110706169/207207310-b1607b11-0338-4f31-8e30-31cfe2d65482.png)
  
   * The **balance_accuracy_score** is: 79%
    
   ![image](https://user-images.githubusercontent.com/110706169/207207371-96cb2366-1b50-4bad-bead-e684632cff89.png)

   <kbd>![image](https://user-images.githubusercontent.com/110706169/207431154-7d1e2f83-00f4-4aa9-b349-c2fb80a52603.png)</kbd>
  
  * Precision High Risk: 4%
  * Precision Low Risk: 100%
  * Recall High Risk: 67%
  * Recall Low Risk: 91%
  
   ### EasyEnsembleClassifier
   
   * Bag of balanced boosted learners also known as EasyEnsemble.
   
   ![image](https://user-images.githubusercontent.com/110706169/207207465-12f41efe-6c7b-4123-8308-405f1d980b05.png)
  
   ![image](https://user-images.githubusercontent.com/110706169/207207505-df1e01b7-76c3-4849-be1b-01944cb4b5dd.png)
  
   * The **balance_accuracy_score** is: 93%
    
   ![image](https://user-images.githubusercontent.com/110706169/207207536-4934eb0c-c231-4f99-b438-10fb00a76038.png)

  <kbd>![image](https://user-images.githubusercontent.com/110706169/207431282-ff0b05f4-f6b8-4f30-8de1-4e892b6b5778.png)</kbd>
  
  * Precision High Risk: 7%
  * Precision Low Risk: 100%
  * Recall High Risk: 91%
  * Recall Low Risk: 94%
  
  
## Summary

### Models by Performance

|          model         | accuracy_score | f1 score|
|         :----:         |      :---:     |   :----:| 
| EasyEnsembleClassifier | 93%            | 97%     |
| BalancedRandomForestClassifier | 79%            | 95%     |
| SMOTE | 65%            | 79%     |
| SMOTEENN | 65%            | 73%     |
| RandomOverSampler | 62%            | 78%     |
| ClusterCentroids | 51%            | 60%     |

From the table above, we can conclude that the EasyEnsembleClassifier is the best model for this dataset with an accuracy score of 93% and f1 score of 97%. All of our models have a Precision Low Risk of 100%; however, EEC has the highest precision for identifying credit risk at 7%. 
    
**EasyEnsembleClassifier**

![image](https://user-images.githubusercontent.com/110706169/207207536-4934eb0c-c231-4f99-b438-10fb00a76038.png)

**ClusterCentroids**

![image](https://user-images.githubusercontent.com/110706169/207206618-afb4b29a-ce64-4384-8b61-5cab44da3a69.png)

After comparing confusion matrices between EEC(best model) and CC(worst model) we demonstrate just how much more effective our EasyEnsembleClassifier model is at predicting risk factors.
