# oci_email_suppression

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
module "oci_email_suppression" {
  source = "./modules/oci/r/oci_email_suppression"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # email_address - (required) is a type of string
  email_address = null

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

variable "email_address" {
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
resource "oci_email_suppression" "this" {
  compartment_id = var.compartment_id
  email_address  = var.email_address

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
  value       = oci_email_suppression.this.id
}

output "reason" {
  description = "returns a string"
  value       = oci_email_suppression.this.reason
}

output "time_created" {
  description = "returns a string"
  value       = oci_email_suppression.this.time_created
}

output "this" {
  value = oci_email_suppression.this
}
```

[top](#index)