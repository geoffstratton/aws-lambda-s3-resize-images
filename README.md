Repo Name
=========
aws-lambda-s3-resize-images

Description
---------------
AWS Lambda script for resizing images on upload to an S3 bucket. Uses Python (tested with 3.7), Amazon's boto3 SDK, the PIL image library, and a Lambda trigger.

Prerequisites
---------------
* The [boto3 SDK](https://aws.amazon.com/sdk-for-python/).
* The [Pillow](https://pypi.org/project/Pillow/) image library.
* Ensure that the IAM Role attached to the Lambda function has a policy for S3 access. If you want to create a custom policy, include:
   + s3.GetObject
   + s3.PutObject
* Ensure that uploads to your S3 bucket have a trigger for your Lambda function.
* Remember to set your DEST_BUCKET environment variable to where you want your thumbnail to go.

### To set up boto3 for development (Amazon Linux and similar):
```
sudo yum install -y python3 python3-pip python3-setuptools
pip3 install boto3 --user
aws configure [enter your AWS access key and secret key]

python3
>>> import boto3
>>> ec2 = boto3.client('ec2')
>>> response = ec2.run_instances(ImageId='ami-00dc79254d0461090',InstanceType='t2.micro',KeyName='MY KEY',MinCount=1,MaxCount=1)
```

License
---------------
GNU General Public License v3.0
