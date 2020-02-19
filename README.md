# ami

## Creating an AMI using Hashicorp Packer

**Circle CI Environment Variables**

1. AWS_ACCESS_KEY
2. AWS_SECRET_KEY
3. AWS_REGION
4. AWS_USER
5. SOURCE_AMI

_Packer Template name_ : `ubuntu-ami.json`

**Validate the Packer Template**
`packer validate -var source_ami="ami_Id" ubuntu-ami.json`


**Run Packer Template to generate AMI locally**

1. Provide all the parameter inside vars.json file.
    -   "aws_region": "Region where the AMI would be created",
    -   "aws_access_key": "AWS Access key of user",
    -   "aws_secret_key": "AWS Secret key of user",
    -   "subnet_id": "Leave it blank for default VPC else provide the id",
    -   "source_ami": "Source AMI as base",
    -   "ami_users": "User if with whom this new AMI will be shared"

2. Run the following command.

`packer build -var-file=./vars.json ubuntu-ami.json`


