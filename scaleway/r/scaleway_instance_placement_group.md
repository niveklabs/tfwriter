# scaleway_instance_placement_group

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_instance_placement_group" {
  source = "./modules/scaleway/r/scaleway_instance_placement_group"

  # name - (optional) is a type of string
  name = null
  # policy_mode - (optional) is a type of string
  policy_mode = null
  # policy_type - (optional) is a type of string
  policy_type = null
  # project_id - (optional) is a type of string
  project_id = null
  # zone - (optional) is a type of string
  zone = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - The name of the placement group"
  type        = string
  default     = null
}

variable "policy_mode" {
  description = "(optional) - One of the two policy_mode may be selected: enforced or optional."
  type        = string
  default     = null
}

variable "policy_type" {
  description = "(optional) - The operating mode is selected by a policy_type"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_instance_placement_group" "this" {
  name        = var.name
  policy_mode = var.policy_mode
  policy_type = var.policy_type
  project_id  = var.project_id
  zone        = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = scaleway_instance_placement_group.this.id
}

output "name" {
  description = "returns a string"
  value       = scaleway_instance_placement_group.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_instance_placement_group.this.organization_id
}

output "policy_respected" {
  description = "returns a bool"
  value       = scaleway_instance_placement_group.this.policy_respected
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_instance_placement_group.this.project_id
}

output "zone" {
  description = "returns a string"
  value       = scaleway_instance_placement_group.this.zone
}

output "this" {
  value = scaleway_instance_placement_group.this
}
```

[top](#index)