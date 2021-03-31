# ecl_baremetal_flavor_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_baremetal_flavor_v2" {
  source = "./modules/ecl/d/ecl_baremetal_flavor_v2"

  # disk - (optional) is a type of number
  disk = null
  # name - (optional) is a type of string
  name = null
  # ram - (optional) is a type of number
  ram = null
  # vcpus - (optional) is a type of number
  vcpus = null
}
```

[top](#index)

### Variables

```terraform
variable "disk" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ram" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vcpus" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_baremetal_flavor_v2" "this" {
  disk  = var.disk
  name  = var.name
  ram   = var.ram
  vcpus = var.vcpus
}
```

[top](#index)

### Outputs

```terraform
output "disk" {
  description = "returns a number"
  value       = data.ecl_baremetal_flavor_v2.this.disk
}

output "id" {
  description = "returns a string"
  value       = data.ecl_baremetal_flavor_v2.this.id
}

output "name" {
  description = "returns a string"
  value       = data.ecl_baremetal_flavor_v2.this.name
}

output "ram" {
  description = "returns a number"
  value       = data.ecl_baremetal_flavor_v2.this.ram
}

output "vcpus" {
  description = "returns a number"
  value       = data.ecl_baremetal_flavor_v2.this.vcpus
}

output "this" {
  value = ecl_baremetal_flavor_v2.this
}
```

[top](#index)