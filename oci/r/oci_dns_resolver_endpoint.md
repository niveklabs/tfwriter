# oci_dns_resolver_endpoint

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dns_resolver_endpoint" {
  source = "./modules/oci/r/oci_dns_resolver_endpoint"

  # endpoint_type - (optional) is a type of string
  endpoint_type = null
  # forwarding_address - (optional) is a type of string
  forwarding_address = null
  # is_forwarding - (required) is a type of bool
  is_forwarding = null
  # is_listening - (required) is a type of bool
  is_listening = null
  # listening_address - (optional) is a type of string
  listening_address = null
  # name - (required) is a type of string
  name = null
  # nsg_ids - (optional) is a type of set of string
  nsg_ids = []
  # resolver_id - (required) is a type of string
  resolver_id = null
  # scope - (required) is a type of string
  scope = null
  # subnet_id - (required) is a type of string
  subnet_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "endpoint_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forwarding_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_forwarding" {
  description = "(required)"
  type        = bool
}

variable "is_listening" {
  description = "(required)"
  type        = bool
}

variable "listening_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "resolver_id" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_dns_resolver_endpoint" "this" {
  endpoint_type      = var.endpoint_type
  forwarding_address = var.forwarding_address
  is_forwarding      = var.is_forwarding
  is_listening       = var.is_listening
  listening_address  = var.listening_address
  name               = var.name
  nsg_ids            = var.nsg_ids
  resolver_id        = var.resolver_id
  scope              = var.scope
  subnet_id          = var.subnet_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = oci_dns_resolver_endpoint.this.compartment_id
}

output "endpoint_type" {
  description = "returns a string"
  value       = oci_dns_resolver_endpoint.this.endpoint_type
}

output "forwarding_address" {
  description = "returns a string"
  value       = oci_dns_resolver_endpoint.this.forwarding_address
}

output "id" {
  description = "returns a string"
  value       = oci_dns_resolver_endpoint.this.id
}

output "listening_address" {
  description = "returns a string"
  value       = oci_dns_resolver_endpoint.this.listening_address
}

output "self" {
  description = "returns a string"
  value       = oci_dns_resolver_endpoint.this.self
}

output "state" {
  description = "returns a string"
  value       = oci_dns_resolver_endpoint.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_dns_resolver_endpoint.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_dns_resolver_endpoint.this.time_updated
}

output "this" {
  value = oci_dns_resolver_endpoint.this
}
```

[top](#index)