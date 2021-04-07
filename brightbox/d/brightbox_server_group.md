# brightbox_server_group

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
module "brightbox_server_group" {
  source = "./modules/brightbox/d/brightbox_server_group"

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
  description = "(optional) - User Description"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - User Label"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "brightbox_server_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "default" {
  description = "returns a bool"
  value       = data.brightbox_server_group.this.default
}

output "description" {
  description = "returns a string"
  value       = data.brightbox_server_group.this.description
}

output "fqdn" {
  description = "returns a string"
  value       = data.brightbox_server_group.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = data.brightbox_server_group.this.id
}

output "name" {
  description = "returns a string"
  value       = data.brightbox_server_group.this.name
}

output "this" {
  value = brightbox_server_group.this
}
```

[top](#index)