# aws_ec2_spot_price
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)
### Terraform
```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```
[top](#index)
### Example Usage
```hcl
module "aws_ec2_spot_price" {
  source = "./modules/aws/d/aws_ec2_spot_price"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # instance_type - (optional) is a type of string
  instance_type = null

  filter = [{
    name   = null
    values = []
  }]
}
```
[top](#index)
### Variables
```hcl
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```
[top](#index)

### Datasource
```hcl
data "aws_ec2_spot_price" "this" {
  availability_zone = var.availability_zone
  instance_type     = var.instance_type

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      values = filter.value["values"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = data.aws_ec2_spot_price.this.id
}

output "spot_price" {
  description = "returns a string"
  value       = data.aws_ec2_spot_price.this.spot_price
}

output "spot_price_timestamp" {
  description = "returns a string"
  value       = data.aws_ec2_spot_price.this.spot_price_timestamp
}

output "this" {
  value = aws_ec2_spot_price.this
}
```
[top](#index)
