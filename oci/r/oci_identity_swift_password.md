# oci_identity_swift_password

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
module "oci_identity_swift_password" {
  source = "./modules/oci/r/oci_identity_swift_password"

  # description - (required) is a type of string
  description = null
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
variable "description" {
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
resource "oci_identity_swift_password" "this" {
  description = var.description
  user_id     = var.user_id

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
output "expires_on" {
  description = "returns a string"
  value       = oci_identity_swift_password.this.expires_on
}

output "id" {
  description = "returns a string"
  value       = oci_identity_swift_password.this.id
}

output "inactive_state" {
  description = "returns a string"
  value       = oci_identity_swift_password.this.inactive_state
}

output "password" {
  description = "returns a string"
  value       = oci_identity_swift_password.this.password
}

output "state" {
  description = "returns a string"
  value       = oci_identity_swift_password.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_swift_password.this.time_created
}

output "this" {
  value = oci_identity_swift_password.this
}
```

[top](#index)