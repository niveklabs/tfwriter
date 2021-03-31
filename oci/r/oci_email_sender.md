# oci_email_sender

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
module "oci_email_sender" {
  source = "./modules/oci/r/oci_email_sender"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # email_address - (required) is a type of string
  email_address = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}

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

variable "email_address" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
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
resource "oci_email_sender" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  email_address  = var.email_address
  freeform_tags  = var.freeform_tags

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
  value       = oci_email_sender.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_email_sender.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_email_sender.this.id
}

output "is_spf" {
  description = "returns a bool"
  value       = oci_email_sender.this.is_spf
}

output "state" {
  description = "returns a string"
  value       = oci_email_sender.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_email_sender.this.time_created
}

output "this" {
  value = oci_email_sender.this
}
```

[top](#index)