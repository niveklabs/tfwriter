# oci_dns_tsig_key

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dns_tsig_key" {
  source = "./modules/oci/r/oci_dns_tsig_key"

  # algorithm - (required) is a type of string
  algorithm = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # name - (required) is a type of string
  name = null
  # secret - (required) is a type of string
  secret = null

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
variable "algorithm" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "secret" {
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
resource "oci_dns_tsig_key" "this" {
  algorithm      = var.algorithm
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  freeform_tags  = var.freeform_tags
  name           = var.name
  secret         = var.secret

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_dns_tsig_key.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_dns_tsig_key.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_dns_tsig_key.this.id
}

output "self" {
  description = "returns a string"
  value       = oci_dns_tsig_key.this.self
}

output "state" {
  description = "returns a string"
  value       = oci_dns_tsig_key.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_dns_tsig_key.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_dns_tsig_key.this.time_updated
}

output "this" {
  value = oci_dns_tsig_key.this
}
```

[top](#index)