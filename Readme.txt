## Compare registry experiments mlflow vs vertex AI

Folders:
- vertex_ai: how to registry runs of training models using vertex experiments
- mlflow: how to registry runs of training models using mlflow - in this example are used a locally version of mlflow

- extra_set_mlflow_cloudrun: In addition, there is a extra folder that show how to have a mlflow serverless running in a cloud run. But there is a problem that the parameters and metrics are hosted in the cloud run and when it shutdown the information are losed