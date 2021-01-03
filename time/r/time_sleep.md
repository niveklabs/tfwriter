# time_sleep

[back](../time.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    time = ">= 0.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "time_sleep" {
  source = "./modules/time/r/time_sleep"

  # create_duration - (optional) is a type of string
  create_duration = null
  # destroy_duration - (optional) is a type of string
  destroy_duration = null
  # triggers - (optional) is a type of map of string
  triggers = {}
}
```

[top](#index)

### Variables

```terraform
variable "create_duration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destroy_duration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "triggers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "time_sleep" "this" {
  create_duration  = var.create_duration
  destroy_duration = var.destroy_duration
  triggers         = var.triggers
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = time_sleep.this.id
}

output "this" {
  value = time_sleep.this
}
```

[top](#index)