# Quick Start Link
_requires bucket and files first (see bucket policy below)_

[![Launch Stack](../images/launchstack.png)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/quickcreate?templateUrl=https%3A%2F%2Fperforce-aws-gametech-cfn-templates-1.s3.us-east-1.amazonaws.com%2Faws-perforce%2Ftemplates%2FPerforceTemplateMain.yaml&stackName=Perforce-Workstation-POC-1&param_AccessCIDR=0.0.0.0%2F0&param_DepotVolumeSize=1024&param_DepotVolumeType=gp2&param_EnableReplica=No&param_InstanceType=t3.micro&param_KeyPairName=rlitalien-perforce-key&param_LatestAmiId=ami-08a702a5b23838980&param_LatestWorkstationAmiId=ami-059ac5410b2a0c8b9&param_LogVolumeSize=128&param_MetadataVolumeSize=64&param_MetadataVolumeType=gp2&param_QSS3BucketName=perforce-aws-gametech-cfn-templates-1&param_QSS3BucketRegion=us-east-1&param_QSS3KeyPrefix=aws-perforce%2F)

## Bucket and files to create/copy

```
* S3/perforce-aws-gametech-cfn-templates-1/aws-perforce/templates
* S3/perforce-aws-gametech-cfn-templates-1/aws-perforce/templates/PerforceServerSetupTemplate.yaml
* S3/perforce-aws-gametech-cfn-templates-1/aws-perforce/templates/PerforceTemplateMain.yaml
* S3/perforce-aws-gametech-cfn-templates-1/aws-perforce/templates/PerforceVPCTemplate.yaml
```

## Quick base links

* aws-perforce - AWS templates:
  * `https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/template?stackName=AWSPerforceTest&templateURL=https://gametech-cfn-templates-public.s3.amazonaws.com/aws-perforce/templates/PerforceTemplateMain.yaml`
* aws-perforce - Perforce templates: 
  * `https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/template?stackName=AWSPerforceTest&templateURL=https://perforce-aws-gametech-cfn-templates-1.s3.us-east-1.amazonaws.com/aws-perforce/templates/PerforceTemplateMain.yaml`



### Bucket Policy
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicRead",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject",
                "s3:GetObjectVersion"
            ],
            "Resource": [
                "arn:aws:s3:::perforce-aws-gametech-cfn-templates-1",
                "arn:aws:s3:::perforce-aws-gametech-cfn-templates-1/*"
            ]
        }
    ]
}
```