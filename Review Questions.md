## Chapter 2

| index | My Answer | Ground Truth |
| ----- | --------- | ------------ |
| 1     | B         |              |
| 2     | D         |              |
| 3     | A         | B            |
| 4     | A         |              |
| 5     | A         | B            |
| 6     | B         | D            |
| 7     | B         |              |
| 8     | A         |              |
| 9     | D         |              |
| 10    | D         |              |
| 11    | A         |              |
| 12    | C         |              |
| 13    | B         |              |
| 14    | C         |              |
| 15    | B         |              |
| 16    | A         |              |
| 17    | B         |              |
| 18    | B, C      |              |
| 19    | A, B      |              |
| 20    | B         |              |

3. A marketing data provider has 50 GB of time series data from various customers and would like to train a forecasting model to predict future sales. The customer uses an open-source algorithm on premises and is exploring ways to build multiple forecasting models based on cohorts of customers. Which of these solutions will work for this company?
	- Use the open-source algorithms on SageMaker either by using Script Mode or by bringing in a custom container and pointing the training job to data on S3.
	
5. A customer currently uses Spark on premises to transform datasets for machine learning purposes. The customer is new to AWS and is aware of training options that are available on SageMaker. The customer would like to reuse Spark code that they have developed as is butmake it part of their machine learning lifecycle on AWS. What solution will require the least amount of maintenance and would integrate well with other steps in the machine learning lifecycle?
	- Use the Spark processing container provided by SageMaker and prepare data for training steps that will also use SageMaker.

6. A customer running a streaming service has 10,000 audio files in S3. The customer would like to easily label these audio files and use them in a deep learning algorithm for music genre classification. Which solution will allow the customer to achieve this?
	- Use a custom UI template for audio classification on SageMaker GroundTruth, followed by a custom audio classification algorithm to train the model.