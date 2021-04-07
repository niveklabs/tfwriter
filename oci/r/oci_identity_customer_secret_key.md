# oci_identity_customer_secret_key

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
module "oci_identity_customer_secret_key" {
  source = "./modules/oci/r/oci_identity_customer_secret_key"

  # display_name - (required) is a type of string
  display_name = null
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
variable "display_name" {
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
resource "oci_identity_customer_secret_key" "this" {
  display_name = var.display_name
  user_id      = var.user_id

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
output "id" {
  description = "returns a string"
  value       = oci_identity_customer_secret_key.this.id
}

output "inactive_state" {
  description = "returns a string"
  value       = oci_identity_customer_secret_key.this.inactive_state
}

output "key" {
  description = "returns a string"
  value       = oci_identity_customer_secret_key.this.key
}

output "state" {
  description = "returns a string"
  value       = oci_identity_customer_secret_key.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_customer_secret_key.this.time_created
}

output "time_expires" {
  description = "returns a string"
  value       = oci_identity_customer_secret_key.this.time_expires
}

output "this" {
  value = oci_identity_customer_secret_key.this
}
```

[top](#index)