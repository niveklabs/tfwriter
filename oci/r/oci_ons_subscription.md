# oci_ons_subscription

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
module "oci_ons_subscription" {
  source = "./modules/oci/r/oci_ons_subscription"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # delivery_policy - (optional) is a type of string
  delivery_policy = null
  # endpoint - (required) is a type of string
  endpoint = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # protocol - (required) is a type of string
  protocol = null
  # topic_id - (required) is a type of string
  topic_id = null

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

variable "delivery_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "topic_id" {
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
resource "oci_ons_subscription" "this" {
  compartment_id  = var.compartment_id
  defined_tags    = var.defined_tags
  delivery_policy = var.delivery_policy
  endpoint        = var.endpoint
  freeform_tags   = var.freeform_tags
  protocol        = var.protocol
  topic_id        = var.topic_id

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
output "created_time" {
  description = "returns a string"
  value       = oci_ons_subscription.this.created_time
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_ons_subscription.this.defined_tags
}

output "delivery_policy" {
  description = "returns a string"
  value       = oci_ons_subscription.this.delivery_policy
}

output "etag" {
  description = "returns a string"
  value       = oci_ons_subscription.this.etag
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_ons_subscription.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_ons_subscription.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_ons_subscription.this.state
}

output "this" {
  value = oci_ons_subscription.this
}
```

[top](#index)