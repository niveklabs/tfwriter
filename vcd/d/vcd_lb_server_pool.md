# vcd_lb_server_pool

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
module "vcd_lb_server_pool" {
  source = "./modules/vcd/d/vcd_lb_server_pool"

  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "edge_gateway" {
  description = "(required) - Edge gateway name in which the LB Server Pool is located"
  type        = string
}

variable "name" {
  description = "(required) - Server Pool name for lookup"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_lb_server_pool" "this" {
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "algorithm" {
  description = "returns a string"
  value       = data.vcd_lb_server_pool.this.algorithm
}

output "algorithm_parameters" {
  description = "returns a string"
  value       = data.vcd_lb_server_pool.this.algorithm_parameters
}

output "description" {
  description = "returns a string"
  value       = data.vcd_lb_server_pool.this.description
}

output "enable_transparency" {
  description = "returns a bool"
  value       = data.vcd_lb_server_pool.this.enable_transparency
}

output "id" {
  description = "returns a string"
  value       = data.vcd_lb_server_pool.this.id
}

output "member" {
  description = "returns a list of object"
  value       = data.vcd_lb_server_pool.this.member
}

output "monitor_id" {
  description = "returns a string"
  value       = data.vcd_lb_server_pool.this.monitor_id
}

output "this" {
  value = vcd_lb_server_pool.this
}
```

[top](#index)