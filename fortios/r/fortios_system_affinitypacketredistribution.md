# fortios_system_affinitypacketredistribution

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_affinitypacketredistribution" {
  source = "./modules/fortios/r/fortios_system_affinitypacketredistribution"

  # affinity_cpumask - (required) is a type of string
  affinity_cpumask = null
  # fosid - (required) is a type of number
  fosid = null
  # interface - (required) is a type of string
  interface = null
  # rxqid - (required) is a type of number
  rxqid = null
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

variable "interface" {
  description = "(required)"
  type        = string
}

variable "rxqid" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_affinitypacketredistribution" "this" {
  affinity_cpumask = var.affinity_cpumask
  fosid            = var.fosid
  interface        = var.interface
  rxqid            = var.rxqid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_affinitypacketredistribution.this.id
}

output "this" {
  value = fortios_system_affinitypacketredistribution.this
}
```

[top](#index)