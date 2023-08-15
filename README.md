# deep-learning-challenge

**Overview:**

Build a tool that can help Alphabet Soup select the applicants for funding with the best chance of success in their ventures.


**Results:**


Data Preprocessing


The target variable for the model: 'IS_SUCCESSFUL'


The feature variables for the model:
        'APPLICATION_TYPE_Other', 'APPLICATION_TYPE_T10',
        'APPLICATION_TYPE_T19', 'APPLICATION_TYPE_T3', 'APPLICATION_TYPE_T4',
        'APPLICATION_TYPE_T5', 'APPLICATION_TYPE_T6', 'APPLICATION_TYPE_T7',
        'APPLICATION_TYPE_T8', 'AFFILIATION_CompanySponsored',
        'AFFILIATION_Family/Parent', 'AFFILIATION_Independent',
        'AFFILIATION_National', 'AFFILIATION_Other', 'AFFILIATION_Regional',
        'CLASSIFICATION_C1000', 'CLASSIFICATION_C1200', 'CLASSIFICATION_C2000',
        'CLASSIFICATION_C2100', 'CLASSIFICATION_C3000', 'CLASSIFICATION_Other',
        'USE_CASE_CommunityServ', 'USE_CASE_Heathcare', 'USE_CASE_Other',
        'USE_CASE_Preservation', 'USE_CASE_ProductDev',
        'ORGANIZATION_Association', 'ORGANIZATION_Co-operative',
        'ORGANIZATION_Corporation', 'ORGANIZATION_Trust', 'INCOME_AMT_0',
        'INCOME_AMT_1-9999', 'INCOME_AMT_10000-24999',
        'INCOME_AMT_100000-499999', 'INCOME_AMT_10M-50M', 'INCOME_AMT_1M-5M',
        'INCOME_AMT_25000-99999', 'INCOME_AMT_50M+', 'INCOME_AMT_5M-10M',
        'SPECIAL_CONSIDERATIONS_N', 'SPECIAL_CONSIDERATIONS_Y'


Variables that are removed from the input data because they are neither targets nor features: 'EIN','NAME'


**Compiling, Training, and Evaluating the Model**

Relu
- number_input_features = X_train_scaled.shape[1]
- hidden_nodes_layer1 =  112
- hidden_nodes_layer2 = 64

--------------------------------------------------------------------------
268/268 - 0s - loss: 0.6359 - accuracy: 0.7279 - 247ms/epoch - 920us/step
Loss: 0.635867714881897, Accuracy: 0.7279300093650818

Relu
- number_input_features = X_train_scaled.shape[1]
- hidden_nodes_layer1 = 32 
- hidden_nodes_layer2 = 8

--------------------------------------------------------------------------
268/268 - 0s - loss: 0.5573 - accuracy: 0.7286 - 316ms/epoch - 1ms/step
Loss: 0.5573371052742004, Accuracy: 0.7286297082901001

LeakyRelu
- number_input_features = X_train_scaled.shape[1]
- hidden_nodes_layer1 = 32 
- hidden_nodes_layer2 = 8

-------------------------------------------------------------------------
268/268 - 0s - loss: 0.5537 - accuracy: 0.7255 - 186ms/epoch - 694us/step
Loss: 0.553698718547821, Accuracy: 0.7254810333251953

ELU

- number_input_features = X_train_scaled.shape[1]
- hidden_nodes_layer1 = 32 
- hidden_nodes_layer2 = 8

-------------------------------------------------------------------------
268/268 - 0s - loss: 0.5543 - accuracy: 0.7290 - 334ms/epoch - 1ms/step
Loss: 0.5543002486228943, Accuracy: 0.7289795875549316

swish

- number_input_features = X_train_scaled.shape[1]
- hidden_nodes_layer1 = 32 
- hidden_nodes_layer2 = 8

--------------------------------------------------------------------------
268/268 - 0s - loss: 0.5535 - accuracy: 0.7313 - 393ms/epoch - 1ms/step
Loss: 0.553458034992218, Accuracy: 0.7213119769096375

LeakyRelu
- number_input_features = X_train_scaled.shape[1]
- hidden_nodes_layer1 = 32 
- hidden_nodes_layer2 = 8
- hidden_nodes_layer3 = 16

--------------------------------------------------------------------------

**Conclusion**

I was able to achieve the best performance with folowing combination:

Relu
- number_input_features = X_train_scaled.shape[1]
- hidden_nodes_layer1 = 41 
- hidden_nodes_layer2 = 21
- hidden_nodes_layer3 = 11
- epochs=150

268/268 - 0s - loss: 0.5621 - accuracy: 0.7301 - 345ms/epoch - 1ms/step
Loss: 0.5620532631874084, Accuracy: 0.7301457524299622


Increasing number of layer or nurons made no difference. Increasing epochs made a slight difference but added significant delay as well. I have tried different activations as well but it hasn't made significant differnce on achieving greater accuracy or reducing loss.
