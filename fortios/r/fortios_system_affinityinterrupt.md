# fortios_system_affinityinterrupt

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_affinityinterrupt" {
  source = "./modules/fortios/r/fortios_system_affinityinterrupt"

  # affinity_cpumask - (required) is a type of string
  affinity_cpumask = null
  # fosid - (required) is a type of number
  fosid = null
  # interrupt - (required) is a type of string
  interrupt = null
}
```

[top](#index)

### Variables

```terraform
variable "affinity_cpumask" {
  description = "(required)"
  type        = string
}

variable "fosid" {
  description = "(required)"
  type        = number
}

variable "interrupt" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_affinityinterrupt" "this" {
  affinity_cpumask = var.affinity_cpumask
  fosid            = var.fosid
  interrupt        = var.interrupt
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_affinityinterrupt.this.id
}

output "this" {
  value = fortios_system_affinityinterrupt.this
}
```

[top](#index)