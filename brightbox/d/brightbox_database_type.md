# brightbox_database_type

[back](../brightbox.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    brightbox = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "brightbox_database_type" {
  source = "./modules/brightbox/d/brightbox_database_type"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of this database type"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of this database type"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "brightbox_database_type" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.brightbox_database_type.this.description
}

output "disk_size" {
  description = "returns a number"
  value       = data.brightbox_database_type.this.disk_size
}

output "id" {
  description = "returns a string"
  value       = data.brightbox_database_type.this.id
}

output "name" {
  description = "returns a string"
  value       = data.brightbox_database_type.this.name
}

output "ram" {
  description = "returns a number"
  value       = data.brightbox_database_type.this.ram
}

output "this" {
  value = brightbox_database_type.this
}
```

[top](#index)