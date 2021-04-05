# thunder_write_memory

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_write_memory" {
  source = "./modules/thunder/r/thunder_write_memory"

  # destination - (optional) is a type of string
  destination = null
  # partition - (optional) is a type of string
  partition = null
  # profile - (optional) is a type of string
  profile = null
  # specified_partition - (optional) is a type of string
  specified_partition = null
}
```

[top](#index)

### Variables

```terraform
variable "destination" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "partition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "specified_partition" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_write_memory" "this" {
  destination         = var.destination
  partition           = var.partition
  profile             = var.profile
  specified_partition = var.specified_partition
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_write_memory.this.id
}

output "this" {
  value = thunder_write_memory.this
}
```

[top](#index)