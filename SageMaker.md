SageMaker can participate in all of the Machine Learning Lifecycle.
- Fetch, clean and prepare data
- Train and evaluate model
- Deploy model, Evaluate results in production

After deploy, new data will be fetch and model wilil be retrained.

## Usage
- spin up training instances, training in large scale.
- Give notebook for data preparation
- Spin up instances in EC2 for deploy model as endpoint.

## Architecture
![[sagemaker_architecture.png]]

## SageMaker Notebook
- Notebook instances on EC2
	- S3 data access
	- Scikit_learn, Spark, Tensorflow
	- Wide variety of built-in models
	- Ability to spin up training instances
	- Ability to deploy trained models for makeing predictions at scale

## Data Preparation
- Data usually comes from [[S3 Data Lakes|S3]]
	- Ideal format varies with Algorithms - often it si RecordIO / [[Protocol Buffer (Protobuf)|protobuf]]
- Can also ingest from [[Athena]], [[EMR]], [[Redshift]]
- [[Apache Spark]] integrates with SageMaker
- scikit_learn, numpy, pandas

## Training
- Creating a training job
	- URL of S3 bucket with training data
	- ML compute resources
	- URL of S3 bucket for output (model / logs)
	- ECR path to training code.
- Training options
	- Built-in training algorithms
	- Algorithms from AWS Marketplace
	- Spark MLLib
	- Custom Python Tensorflow / MXNet code
	- Own Docker image
- DataLoader (Stream to training)
	- File mode
	- Pipe mode (stream, useful for large size data)
 
## Deploying
- Save trained model to S3
- Deploy in two ways
	- Persistent endpoint for making individual predictions on demand.
	- SageMaker Batch Transform to get predictions for an entire dataset
- Cool options
	- Inference Pipelines for more complex processing
	- SageMaker Neo for deploying to edge devices
	- Elastic Inference for accelerating DL Models.
	- Automative scaling (increase # of endpoints as needed)

## Built-in Algorithms 
- [[Linear Learner]], [[XGBoost]], [[DeepAR]], 
- [[Seq2Seq]], [[BlazingText]], [[Object2Vec]], 
- [[Object Detection]], [[Image Classification]],[[ Semantic Segmentation]], 
- [[Random Cut Forest]], [[Neural Topic Model]], [[LDA]], [[KNN]], [[K-Means]], [[PCA]] 
-[[ Factorization Machines]], [[IP Insights]], Reinforcement Learning