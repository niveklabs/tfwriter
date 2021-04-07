# checkpoint_management_set_threat_protection

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_set_threat_protection" {
  source = "./modules/checkpoint/r/checkpoint_management_set_threat_protection"

  # comments - (optional) is a type of string
  comments = null
  # follow_up - (optional) is a type of bool
  follow_up = null
  # name - (required) is a type of string
  name = null

  overrides = [{
    action          = null
    capture_packets = null
    profile         = null
    track           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional) - Protection comments."
  type        = string
  default     = null
}

variable "follow_up" {
  description = "(optional) - Tag the protection with pre-defined follow-up flag."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "overrides" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action          = string
      capture_packets = bool
      profile         = string
      track           = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_set_threat_protection" "this" {
  # comments - (optional) is a type of string
  comments = var.comments
  # follow_up - (optional) is a type of bool
  follow_up = var.follow_up
  # name - (required) is a type of string
  name = var.name

  dynamic "overrides" {
    for_each = var.overrides
    content {
      # action - (optional) is a type of string
      action = overrides.value["action"]
      # capture_packets - (optional) is a type of bool
      capture_packets = overrides.value["capture_packets"]
      # profile - (optional) is a type of string
      profile = overrides.value["profile"]
      # track - (optional) is a type of string
      track = overrides.value["track"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_set_threat_protection.this.id
}

output "this" {
  value = checkpoint_management_set_threat_protection.this
}
```

[top](#index)