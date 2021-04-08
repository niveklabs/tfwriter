# vcd_vm_sizing_policy

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_vm_sizing_policy" {
  source = "./modules/vcd/d/vcd_vm_sizing_policy"

  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_vm_sizing_policy" "this" {
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
}
```

[top](#index)

### Outputs

```terraform
output "cpu" {
  description = "returns a list of object"
  value       = data.vcd_vm_sizing_policy.this.cpu
}

output "description" {
  description = "returns a string"
  value       = data.vcd_vm_sizing_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vcd_vm_sizing_policy.this.id
}

output "memory" {
  description = "returns a list of object"
  value       = data.vcd_vm_sizing_policy.this.memory
}

output "this" {
  value = vcd_vm_sizing_policy.this
}
```

[top](#index)