# aws_wafregional_web_acl
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
module "aws_wafregional_web_acl" {
  source = "./modules/aws/d/aws_wafregional_web_acl"

  # name - (required) is a type of string
  name = null
}
```
[top](#index)
### Variables
```hcl
variable "name" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Datasource
```hcl
data "aws_wafregional_web_acl" "this" {
  name = var.name
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = data.aws_wafregional_web_acl.this.id
}

output "this" {
  value = aws_wafregional_web_acl.this
}
```
[top](#index)
