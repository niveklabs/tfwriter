# vra_network_ip_range

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_network_ip_range" {
  source = "./modules/vra/r/vra_network_ip_range"

  # description - (optional) is a type of string
  description = null
  # end_ip_address - (required) is a type of string
  end_ip_address = null
  # fabric_network_id - (optional) is a type of string
  fabric_network_id = null
  # ip_version - (required) is a type of string
  ip_version = null
  # name - (required) is a type of string
  name = null
  # start_ip_address - (required) is a type of string
  start_ip_address = null

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_ip_address" {
  description = "(required)"
  type        = string
}

variable "fabric_network_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_version" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "start_ip_address" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra_network_ip_range" "this" {
  # description - (optional) is a type of string
  description = var.description
  # end_ip_address - (required) is a type of string
  end_ip_address = var.end_ip_address
  # fabric_network_id - (optional) is a type of string
  fabric_network_id = var.fabric_network_id
  # ip_version - (required) is a type of string
  ip_version = var.ip_version
  # name - (required) is a type of string
  name = var.name
  # start_ip_address - (required) is a type of string
  start_ip_address = var.start_ip_address

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = vra_network_ip_range.this.created_at
}

output "external_id" {
  description = "returns a string"
  value       = vra_network_ip_range.this.external_id
}

output "id" {
  description = "returns a string"
  value       = vra_network_ip_range.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_network_ip_range.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_network_ip_range.this.org_id
}

output "updated_at" {
  description = "returns a string"
  value       = vra_network_ip_range.this.updated_at
}

output "this" {
  value = vra_network_ip_range.this
}
```

[top](#index)