# Cloudformation Custom Resources: DynamoDB Data Ingest

Supporting project for blog at https://janakerman.co.uk/cloudformation-dynamodb-data-ingest.

1. Create Ingest Stack
`aws cloudformation update-stack --stack-name ingest-data --template-body file://./DataIngest.yaml --capabilities CAPABILITY_IAM`

2. Upload `ingestData1.json` to the newly created bucket.

3. Create the DynamoDB table.
`aws cloudformation update-stack --stack-name test --template-body file://./ExampleTable.yaml --parameters ParameterKey=DataIngestStackName,ParameterValue=ingest-data ParameterKey=IngestDataFile,ParameterValue=ingestData1.json`
