# oci_kms_key_version

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_kms_key_version" {
  source = "./modules/oci/r/oci_kms_key_version"

  # key_id - (required) is a type of string
  key_id = null
  # management_endpoint - (required) is a type of string
  management_endpoint = null
  # time_of_deletion - (optional) is a type of string
  time_of_deletion = null

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
variable "key_id" {
  description = "(required)"
  type        = string
}

variable "management_endpoint" {
  description = "(required)"
  type        = string
}

variable "time_of_deletion" {
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
resource "oci_kms_key_version" "this" {
  key_id              = var.key_id
  management_endpoint = var.management_endpoint
  time_of_deletion    = var.time_of_deletion

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
  value       = oci_kms_key_version.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = oci_kms_key_version.this.id
}

output "key_version_id" {
  description = "returns a string"
  value       = oci_kms_key_version.this.key_version_id
}

output "public_key" {
  description = "returns a string"
  value       = oci_kms_key_version.this.public_key
}

output "restored_from_key_id" {
  description = "returns a string"
  value       = oci_kms_key_version.this.restored_from_key_id
}

output "restored_from_key_version_id" {
  description = "returns a string"
  value       = oci_kms_key_version.this.restored_from_key_version_id
}

output "state" {
  description = "returns a string"
  value       = oci_kms_key_version.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_kms_key_version.this.time_created
}

output "time_of_deletion" {
  description = "returns a string"
  value       = oci_kms_key_version.this.time_of_deletion
}

output "vault_id" {
  description = "returns a string"
  value       = oci_kms_key_version.this.vault_id
}

output "this" {
  value = oci_kms_key_version.this
}
```

[top](#index)