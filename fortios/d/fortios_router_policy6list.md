# fortios_router_policy6list

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "fortios_router_policy6list" {
  source = "./modules/fortios/d/fortios_router_policy6list"

  # filter - (optional) is a type of string
  filter = null
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "fortios_router_policy6list" "this" {
  # filter - (optional) is a type of string
  filter = var.filter
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_router_policy6list.this.id
}

output "seq_numlist" {
  description = "returns a list of number"
  value       = data.fortios_router_policy6list.this.seq_numlist
}

output "this" {
  value = fortios_router_policy6list.this
}
```

[top](#index)