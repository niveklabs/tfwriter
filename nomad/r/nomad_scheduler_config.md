# nomad_scheduler_config

[back](../nomad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nomad = ">= 1.4.13"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_scheduler_config" {
  source = "./modules/nomad/r/nomad_scheduler_config"

  # preemption_config - (optional) is a type of map of bool
  preemption_config = {}
  # scheduler_algorithm - (optional) is a type of string
  scheduler_algorithm = null
}
```

[top](#index)

### Variables

```terraform
variable "preemption_config" {
  description = "(optional) - Options to enable preemption for various schedulers."
  type        = map(bool)
  default     = null
}

variable "scheduler_algorithm" {
  description = "(optional) - Specifies whether scheduler binpacks or spreads allocations on available nodes."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "nomad_scheduler_config" "this" {
  preemption_config   = var.preemption_config
  scheduler_algorithm = var.scheduler_algorithm
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nomad_scheduler_config.this.id
}

output "this" {
  value = nomad_scheduler_config.this
}
```

[top](#index)