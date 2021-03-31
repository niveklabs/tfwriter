# oci_identity_api_key

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
module "oci_identity_api_key" {
  source = "./modules/oci/r/oci_identity_api_key"

  # key_value - (required) is a type of string
  key_value = null
  # user_id - (required) is a type of string
  user_id = null

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
variable "key_value" {
  description = "(required)"
  type        = string
}

variable "user_id" {
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
resource "oci_identity_api_key" "this" {
  key_value = var.key_value
  user_id   = var.user_id

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
output "fingerprint" {
  description = "returns a string"
  value       = oci_identity_api_key.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = oci_identity_api_key.this.id
}

output "inactive_status" {
  description = "returns a string"
  value       = oci_identity_api_key.this.inactive_status
}

output "state" {
  description = "returns a string"
  value       = oci_identity_api_key.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_api_key.this.time_created
}

output "this" {
  value = oci_identity_api_key.this
}
```

[top](#index)