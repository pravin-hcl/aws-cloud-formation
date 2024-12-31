### Creating the EC2 using AWS CFT

- Created the EC2 using AWS CFT by referring to the AWS CloudFormation documention.
- Created the Stack and upload this template and created.
- Then modified the name of the ec2 and checked the `detect drift` option and verfied the status and we can see the changes updated from the expected one.

```
Resources:
  EC2Instance:
    Type: AWS::EC2::Instance
    Properties: 
      InstanceType: t2.micro
      ImageId: ami-003f5a76758516d1e
      KeyName: ansible-keypair
      SecurityGroups:
        - default
      Tags:
        - Key: department
          Value: dev
        - Key: Name         # Name of the EC2 instance
          Value: EC2Instance # Value of the Name tag
```

### Creating the s3 bucket using AWS CFT

- Created the S3 Bucket using AWS CFT by referring to the AWS CloudFormation documention.
- Created the Stack and upload this template and created.
- Then modified the versioning of the s3 bucket and checked the `detect drift` option and verfied the status and we can see the changes updated from the expected one.

```
Resources:
  S3Bucket:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: dec-31-bucket-2024
      
      VersioningConfiguration:
        Status: Enabled

      Tags:
        - Key: department
          Value: dev
        - Key: Name
          Value: dec-31-bucket-2024
```

- Check the `ec2_template.yml` file for the complete script.
