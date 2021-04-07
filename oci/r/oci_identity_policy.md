# oci_identity_policy

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
module "oci_identity_policy" {
  source = "./modules/oci/r/oci_identity_policy"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (required) is a type of string
  description = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # name - (required) is a type of string
  name = null
  # statements - (required) is a type of list of string
  statements = []
  # version_date - (optional) is a type of string
  version_date = null

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

variable "description" {
  description = "(required)"
  type        = string
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

variable "statements" {
  description = "(required)"
  type        = list(string)
}

variable "version_date" {
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
resource "oci_identity_policy" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  description    = var.description
  freeform_tags  = var.freeform_tags
  name           = var.name
  statements     = var.statements
  version_date   = var.version_date

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
output "ETag" {
  description = "returns a string"
  value       = oci_identity_policy.this.ETag
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_identity_policy.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_identity_policy.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_identity_policy.this.id
}

output "inactive_state" {
  description = "returns a string"
  value       = oci_identity_policy.this.inactive_state
}

output "lastUpdateETag" {
  description = "returns a string"
  value       = oci_identity_policy.this.lastUpdateETag
}

output "policyHash" {
  description = "returns a string"
  value       = oci_identity_policy.this.policyHash
}

output "state" {
  description = "returns a string"
  value       = oci_identity_policy.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_policy.this.time_created
}

output "version_date" {
  description = "returns a string"
  value       = oci_identity_policy.this.version_date
}

output "this" {
  value = oci_identity_policy.this
}
```

[top](#index)