# aws_glue_catalog_database
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_glue_catalog_database" {
  source = "./modules/aws/r/aws_glue_catalog_database"

  # catalog_id - (optional) is a type of string
  catalog_id = null
  # description - (optional) is a type of string
  description = null
  # location_uri - (optional) is a type of string
  location_uri = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
}
```
[top](#index)
### Variables
```hcl
variable "catalog_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```
[top](#index)

### Resource
```hcl
resource "aws_glue_catalog_database" "this" {
  catalog_id   = var.catalog_id
  description  = var.description
  location_uri = var.location_uri
  name         = var.name
  parameters   = var.parameters
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_glue_catalog_database.this.arn
}

output "catalog_id" {
  description = "returns a string"
  value       = aws_glue_catalog_database.this.catalog_id
}

output "id" {
  description = "returns a string"
  value       = aws_glue_catalog_database.this.id
}

output "this" {
  value = aws_glue_catalog_database.this
}
```
[top](#index)
