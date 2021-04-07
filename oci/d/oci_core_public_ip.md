# oci_core_public_ip

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_public_ip" {
  source = "./modules/oci/d/oci_core_public_ip"

  # ip_address - (optional) is a type of string
  ip_address = null
  # private_ip_id - (optional) is a type of string
  private_ip_id = null

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
variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ip_id" {
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

### Datasource

```terraform
data "oci_core_public_ip" "this" {
  ip_address    = var.ip_address
  private_ip_id = var.private_ip_id

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
  value       = data.oci_core_public_ip.this.assigned_entity_id
}

output "assigned_entity_type" {
  description = "returns a string"
  value       = data.oci_core_public_ip.this.assigned_entity_type
}

output "availability_domain" {
  description = "returns a string"
  value       = data.oci_core_public_ip.this.availability_domain
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_public_ip.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_public_ip.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_public_ip.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_public_ip.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_public_ip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.oci_core_public_ip.this.ip_address
}

output "lifetime" {
  description = "returns a string"
  value       = data.oci_core_public_ip.this.lifetime
}

output "private_ip_id" {
  description = "returns a string"
  value       = data.oci_core_public_ip.this.private_ip_id
}

output "public_ip_pool_id" {
  description = "returns a string"
  value       = data.oci_core_public_ip.this.public_ip_pool_id
}

output "scope" {
  description = "returns a string"
  value       = data.oci_core_public_ip.this.scope
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_public_ip.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_public_ip.this.time_created
}

output "this" {
  value = oci_core_public_ip.this
}
```

[top](#index)