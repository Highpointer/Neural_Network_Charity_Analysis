# Neural Network Charity Analysis • • • • • ⚫
## Overview of the Analysis

This report presents machine learning and neural networks analysis of over 34,000 lines of data to create a binary classifier capable of predicting whether applicants will be successful if funded by Alphabet Soup.

## Results

### ⚫ Data Preprocessing

#### • The following variable is considered as the target of the analysis:

• <b>IS_SUCCESSFUL</b> - whether or not the money was used successfully

#### • The following variables are considered as the features of the analysis:

  • <b>APPLICATION_TYPE</b> - Alphabet Soup application type

  • <b>AFFILIATION</b> — Affiliated sector of industry

  • <b>CLASSIFICATION</b> — Government organization classification

  • <b>USE_CASE</b> — Use case for funding

  • <b>ORGANIZATION</b> — Organization type

  • <b>STATUS</b> — Active status

  • <b>INCOME_AMT</b> — Income classification

  • <b>SPECIAL_CONSIDERATIONS</b> — Special consideration for application

  • <b>ASK_AMT</b> — Funding amount requested

#### • The following variables are neither targets nor features and are being removed from the input analysis:

  • <b>EIN</b> - Unique identification number

  • <b>NAME</b> — Name of donor
  
Here is what the first five rows of the DataFrame looks like after initial processing:

![DataFrame](Deliverable1DataFrame.png)

### ⚫ Compiling, Training, and Evaluating the Model

#### • How many neurons, layers, and activation functions selected for neural network model, and why?

• The initial analysis includes two (2) hidden layers. The first layer will include 80 neurons and the second layer will include 30 neurons. Initial input functions for the hidden layers are ReLU and the function for the outpuut layer is sigmoid. I selected these number of layers, number of neurons, and functions to be used because they were suggested in the starter code. With 5,981 paramaters, this formulation was complex enough so that strong results would likely to be achieved, but not so complex that computational time would not be excessive and there would be a lower risk of overfitting. Here is the code for the first analysis:

![FirstCode](Code1.png)

Here are the results of the initial analysis:

![First Results](ModelOutput1_revised.png)

The initial accuracy is approximately 72.5%. Our goal is to achieve an accuracy of 75% or better. 

#### • Steps to try and increase model performance

##### To improve accuracy, we could consider several options, with a few to consider as follows:

• Adding a third layer

• Increasing number of neurons per layer

• Changing the input functions to be used

We will add a third layer, and increase the number of neurons to 100 and 50 for the first and second layers, respectively, and add 30 neurons for the third layer. This results in 11,011 parameters. Here is the code for this analysis: 

![SecondCode](Code2.png)

Here are the results:

![Second Results](ModelOutput2.png)

The accuracy remained essentially unchanged at 72.5%. Therefore, adding an additional layer and more neurons does not improve accuracy. Computational time increases with no benefit to the final results.

In the next test, we go back to inputs of the original analysis, using two hidden layers with 80 and 30 neurons, respectively. However, we change the input functions of the hidden layers from ReLU to tanh. Here are the results:

![Third Results](ModelOutput3.png)

There is only a modest increase in accuracy to 72.7%, so the improvement in results by changing the input function is relatively negligible. 

Changing both of the input functions to sigmoid yields about the same results, at 72.6%:

![Fourth Results](ModelOutput4.png)

One more change considered was increasing the number of bins for <b>APPLICATION_TYPE</b> by putting only those values with less than 10 in the "Other" bin (rather than under 200) and increasing the number of bins for <b>CLASSIFICATION</b> by putting only those values with less than 100 in the "Other" bin (rather than under 1000). This yielded an accuracy of 72.4%, about the same or slightly worse, so increasing bin size would not be an advisable strategy.

![Fifth Results](ModelOutput5.png)

#### • Did our analysis achieve target model performance?

The various revisions to the analyses described above did not appreciably improve model performance. The initial analyis yieled 72.5%, but the best increase in accuracy was only to 72.5%.

### ⚫ Summary

It appears that the steps taken above were not effective in reaching the target model performance. The machine learning algorithms considered in this report failed to improve accuracy by more than 72.7%. Therefore, additional machine learning algorithms may need to be considered for future analysis. 

A brief survey of research data indicates that data scientists have designed a wide variety of machine learning algorithms, and additional studies and research are revealing more algoritims that can be applied to the field of machine learning. Other algorithms to consider include support vector machines (SVM) and random forest algorithms. 
