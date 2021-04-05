# panos_bgp_conditional_adv

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_bgp_conditional_adv" {
  source = "./modules/panos/r/panos_bgp_conditional_adv"

  # enable - (optional) is a type of bool
  enable = null
  # name - (required) is a type of string
  name = null
  # used_by - (optional) is a type of list of string
  used_by = []
  # virtual_router - (required) is a type of string
  virtual_router = null
}
```

[top](#index)

### Variables

```terraform
variable "enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "used_by" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "virtual_router" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_bgp_conditional_adv" "this" {
  enable         = var.enable
  name           = var.name
  used_by        = var.used_by
  virtual_router = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_bgp_conditional_adv.this.id
}

output "this" {
  value = panos_bgp_conditional_adv.this
}
```

[top](#index)