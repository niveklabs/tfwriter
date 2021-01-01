# aws_servicequotas_service
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
module "aws_servicequotas_service" {
  source = "./modules/aws/d/aws_servicequotas_service"

  # service_name - (required) is a type of string
  service_name = null
}
```
[top](#index)
### Variables
```hcl
variable "service_name" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Datasource
```hcl
data "aws_servicequotas_service" "this" {
  service_name = var.service_name
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = data.aws_servicequotas_service.this.id
}

output "service_code" {
  description = "returns a string"
  value       = data.aws_servicequotas_service.this.service_code
}

output "this" {
  value = aws_servicequotas_service.this
}
```
[top](#index)
