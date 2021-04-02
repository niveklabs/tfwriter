# oci_identity_user

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
module "oci_identity_user" {
  source = "./modules/oci/r/oci_identity_user"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (required) is a type of string
  description = null
  # email - (optional) is a type of string
  email = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # name - (required) is a type of string
  name = null

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
  description = "(optional)"
  type        = string
  default     = null
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

variable "email" {
  description = "(optional)"
  type        = string
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
resource "oci_identity_user" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  description    = var.description
  email          = var.email
  freeform_tags  = var.freeform_tags
  name           = var.name

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
output "capabilities" {
  description = "returns a list of object"
  value       = oci_identity_user.this.capabilities
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_identity_user.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_identity_user.this.defined_tags
}

output "email" {
  description = "returns a string"
  value       = oci_identity_user.this.email
}

output "email_verified" {
  description = "returns a bool"
  value       = oci_identity_user.this.email_verified
}

output "external_identifier" {
  description = "returns a string"
  value       = oci_identity_user.this.external_identifier
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_identity_user.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_identity_user.this.id
}

output "identity_provider_id" {
  description = "returns a string"
  value       = oci_identity_user.this.identity_provider_id
}

output "inactive_state" {
  description = "returns a string"
  value       = oci_identity_user.this.inactive_state
}

output "last_successful_login_time" {
  description = "returns a string"
  value       = oci_identity_user.this.last_successful_login_time
}

output "previous_successful_login_time" {
  description = "returns a string"
  value       = oci_identity_user.this.previous_successful_login_time
}

output "state" {
  description = "returns a string"
  value       = oci_identity_user.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_user.this.time_created
}

output "this" {
  value = oci_identity_user.this
}
```

[top](#index)