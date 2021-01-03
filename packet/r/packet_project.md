# packet_project

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_project" {
  source = "./modules/packet/r/packet_project"

  # backend_transfer - (optional) is a type of bool
  backend_transfer = null
  # name - (required) is a type of string
  name = null
  # organization_id - (optional) is a type of string
  organization_id = null
  # payment_method_id - (optional) is a type of string
  payment_method_id = null

  bgp_config = [{
    asn             = null
    deployment_type = null
    max_prefix      = null
    md5             = null
    status          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "backend_transfer" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "organization_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "payment_method_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bgp_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      asn             = number
      deployment_type = string
      max_prefix      = number
      md5             = string
      status          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "packet_project" "this" {
  backend_transfer  = var.backend_transfer
  name              = var.name
  organization_id   = var.organization_id
  payment_method_id = var.payment_method_id

  dynamic "bgp_config" {
    for_each = var.bgp_config
    content {
      asn             = bgp_config.value["asn"]
      deployment_type = bgp_config.value["deployment_type"]
      md5             = bgp_config.value["md5"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = packet_project.this.created
}

output "id" {
  description = "returns a string"
  value       = packet_project.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = packet_project.this.organization_id
}

output "payment_method_id" {
  description = "returns a string"
  value       = packet_project.this.payment_method_id
}

output "updated" {
  description = "returns a string"
  value       = packet_project.this.updated
}

output "this" {
  value = packet_project.this
}
```

[top](#index)