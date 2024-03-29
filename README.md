# Spark on AWS EMR Example
An example of running Spark on AWS EMR. Adapated from this [tutorial](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-gs.html).

## Running the example

To run the project locally:

1. Prepare data for S3 upload: `make all`
1. Run Spark application: `python3 src/health_violations.py --data_source data/food_establishment_data.csv --output_uri data`
1. See results: `cat data/part-*.csv`

To run on AWS EMR:

1. Prepare data for S3 upload: `make all`
1. Create a config file with a random bucket name: `bin/create-config`
1. Upload data and script to S3: `bin/upload-files`
1. Create cluster: `bin/create-cluster`
1. Submit application: `bin/submit-application`
1. Download output data: `bin/download-output`
1. See results: `cat data/part-*.csv`

## License
This project is distributed under the MIT license. Please see `LICENSE` for more information.
