# aws_guardduty_detector
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
module "aws_guardduty_detector" {
  source = "./modules/aws/d/aws_guardduty_detector"

}
```
[top](#index)
### Variables
```hcl
```
[top](#index)

### Datasource
```hcl
data "aws_guardduty_detector" "this" {
}
```
[top](#index)
### Outputs
```hcl
output "finding_publishing_frequency" {
  description = "returns a string"
  value       = data.aws_guardduty_detector.this.finding_publishing_frequency
}

output "id" {
  description = "returns a string"
  value       = data.aws_guardduty_detector.this.id
}

output "service_role_arn" {
  description = "returns a string"
  value       = data.aws_guardduty_detector.this.service_role_arn
}

output "status" {
  description = "returns a string"
  value       = data.aws_guardduty_detector.this.status
}

output "this" {
  value = aws_guardduty_detector.this
}
```
[top](#index)
