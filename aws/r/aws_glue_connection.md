# aws_glue_connection

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_glue_connection" {
  source = "./modules/aws/r/aws_glue_connection"

  # catalog_id - (optional) is a type of string
  catalog_id = null
  # connection_properties - (required) is a type of map of string
  connection_properties = {}
  # connection_type - (optional) is a type of string
  connection_type = null
  # description - (optional) is a type of string
  description = null
  # match_criteria - (optional) is a type of list of string
  match_criteria = []
  # name - (required) is a type of string
  name = null

  physical_connection_requirements = [{
    availability_zone      = null
    security_group_id_list = []
    subnet_id              = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "catalog_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "connection_properties" {
  description = "(required)"
  type        = map(string)
}

variable "connection_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "match_criteria" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "physical_connection_requirements" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      availability_zone      = string
      security_group_id_list = set(string)
      subnet_id              = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_glue_connection" "this" {
  catalog_id            = var.catalog_id
  connection_properties = var.connection_properties
  connection_type       = var.connection_type
  description           = var.description
  match_criteria        = var.match_criteria
  name                  = var.name

  dynamic "physical_connection_requirements" {
    for_each = var.physical_connection_requirements
    content {
      availability_zone      = physical_connection_requirements.value["availability_zone"]
      security_group_id_list = physical_connection_requirements.value["security_group_id_list"]
      subnet_id              = physical_connection_requirements.value["subnet_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_glue_connection.this.arn
}

output "catalog_id" {
  description = "returns a string"
  value       = aws_glue_connection.this.catalog_id
}

output "id" {
  description = "returns a string"
  value       = aws_glue_connection.this.id
}

output "this" {
  value = aws_glue_connection.this
}
```

[top](#index)