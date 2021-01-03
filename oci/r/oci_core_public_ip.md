# oci_core_public_ip

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_public_ip" {
  source = "./modules/oci/r/oci_core_public_ip"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # lifetime - (required) is a type of string
  lifetime = null
  # private_ip_id - (optional) is a type of string
  private_ip_id = null
  # public_ip_pool_id - (optional) is a type of string
  public_ip_pool_id = null

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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "lifetime" {
  description = "(required)"
  type        = string
}

variable "private_ip_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_ip_pool_id" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "oci_core_public_ip" "this" {
  compartment_id    = var.compartment_id
  defined_tags      = var.defined_tags
  display_name      = var.display_name
  freeform_tags     = var.freeform_tags
  lifetime          = var.lifetime
  private_ip_id     = var.private_ip_id
  public_ip_pool_id = var.public_ip_pool_id

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
output "assigned_entity_id" {
  description = "returns a string"
  value       = oci_core_public_ip.this.assigned_entity_id
}

output "assigned_entity_type" {
  description = "returns a string"
  value       = oci_core_public_ip.this.assigned_entity_type
}

output "availability_domain" {
  description = "returns a string"
  value       = oci_core_public_ip.this.availability_domain
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_public_ip.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_public_ip.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_public_ip.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_public_ip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = oci_core_public_ip.this.ip_address
}

output "public_ip_pool_id" {
  description = "returns a string"
  value       = oci_core_public_ip.this.public_ip_pool_id
}

output "scope" {
  description = "returns a string"
  value       = oci_core_public_ip.this.scope
}

output "state" {
  description = "returns a string"
  value       = oci_core_public_ip.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_public_ip.this.time_created
}

output "this" {
  value = oci_core_public_ip.this
}
```

[top](#index)