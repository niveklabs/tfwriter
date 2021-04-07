# brightbox_firewall_policy

[back](../brightbox.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    brightbox = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "brightbox_firewall_policy" {
  source = "./modules/brightbox/r/brightbox_firewall_policy"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # server_group - (optional) is a type of string
  server_group = null

  timeouts = [{
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Optional description of the policy"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Optional name for this policy"
  type        = string
  default     = null
}

variable "server_group" {
  description = "(optional) - The server group using this policy"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "brightbox_firewall_policy" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # server_group - (optional) is a type of string
  server_group = var.server_group

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # update - (optional) is a type of string
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
  value       = brightbox_firewall_policy.this.id
}

output "this" {
  value = brightbox_firewall_policy.this
}
```

[top](#index)