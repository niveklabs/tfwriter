# spotinst_subscription

[back](../spotinst.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    spotinst = ">= 1.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "spotinst_subscription" {
  source = "./modules/spotinst/r/spotinst_subscription"

  # endpoint - (required) is a type of string
  endpoint = null
  # event_type - (required) is a type of string
  event_type = null
  # format - (optional) is a type of map of string
  format = {}
  # protocol - (required) is a type of string
  protocol = null
  # resource_id - (required) is a type of string
  resource_id = null
}
```

[top](#index)

### Variables

```terraform
variable "endpoint" {
  description = "(required)"
  type        = string
}

variable "event_type" {
  description = "(required)"
  type        = string
}

variable "format" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_subscription" "this" {
  endpoint    = var.endpoint
  event_type  = var.event_type
  format      = var.format
  protocol    = var.protocol
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = spotinst_subscription.this.id
}

output "this" {
  value = spotinst_subscription.this
}
```

[top](#index)