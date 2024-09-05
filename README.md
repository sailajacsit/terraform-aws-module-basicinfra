
# Terraform AWS Module - Basic Infrastructure

This repository contains a Terraform module that provisions basic AWS infrastructure, including EC2 instances, a VPC, subnets, and security groups.

## Features

- **EC2 Instances**: Configurable with instance type, key pair, and AMI.
- **VPC**: Includes VPC, public/private subnets, and routing.
- **Security Groups**: Manage access control for instances.

## Requirements

- [Terraform](https://www.terraform.io/downloads.html)
- AWS Account

## Usage

```hcl
module "basic_infra" {
  source              = "./module"
  vpc_cidr            = "10.0.0.0/16"
  public_subnet_cidrs = ["10.0.1.0/24"]
  private_subnet_cidrs = ["10.0.2.0/24"]
  instance_type       = "t2.micro"
  ami                 = "ami-0c55b159cbfafe1f0"
  key_name            = "your-key-pair"
}
```

### Steps:

1. **Initialize Terraform**:
   ```bash
   terraform init
   ```
2. **Plan Infrastructure**:
   ```bash
   terraform plan
   ```
3. **Apply Configuration**:
   ```bash
   terraform apply
   ```

### Outputs

- **EC2 Instance Details**: Public IP, private IP, and instance ID.
- **VPC Info**: VPC ID, subnets, and route tables.

## Customization

- Modify `variables.tf` to customize the infrastructure (instance type, CIDR blocks, etc.).

## References

- [Terraform AWS Provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/index.html)
- [AWS VPC Documentation](https://docs.aws.amazon.com/vpc/index.html)
