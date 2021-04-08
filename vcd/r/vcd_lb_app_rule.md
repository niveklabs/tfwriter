# vcd_lb_app_rule

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "vcd_lb_app_rule" {
  source = "./modules/vcd/r/vcd_lb_app_rule"

  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # script - (required) is a type of string
  script = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "edge_gateway" {
  description = "(required) - Edge gateway name in which the LB Application Rule is located"
  type        = string
}

variable "name" {
  description = "(required) - Unique LB Application Rule name"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "script" {
  description = "(required) - The script for the application rule. Note - you may find HEREDOC useful to pass multiline strings"
  type        = string
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vcd_lb_app_rule" "this" {
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # script - (required) is a type of string
  script = var.script
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_lb_app_rule.this.id
}

output "this" {
  value = vcd_lb_app_rule.this
}
```

[top](#index)