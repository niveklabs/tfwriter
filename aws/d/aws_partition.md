# aws_partition
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
module "aws_partition" {
  source = "./modules/aws/d/aws_partition"

}
```
[top](#index)
### Variables
```hcl
```
[top](#index)

### Datasource
```hcl
data "aws_partition" "this" {
}
```
[top](#index)
### Outputs
```hcl
output "dns_suffix" {
  description = "returns a string"
  value       = data.aws_partition.this.dns_suffix
}

output "id" {
  description = "returns a string"
  value       = data.aws_partition.this.id
}

output "partition" {
  description = "returns a string"
  value       = data.aws_partition.this.partition
}

output "this" {
  value = aws_partition.this
}
```
[top](#index)
