# vcd_lb_server_pool

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
module "vcd_lb_server_pool" {
  source = "./modules/vcd/r/vcd_lb_server_pool"

  # algorithm - (required) is a type of string
  algorithm = null
  # algorithm_parameters - (optional) is a type of string
  algorithm_parameters = null
  # description - (optional) is a type of string
  description = null
  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # enable_transparency - (optional) is a type of bool
  enable_transparency = null
  # monitor_id - (optional) is a type of string
  monitor_id = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null

  member = [{
    condition       = null
    id              = null
    ip_address      = null
    max_connections = null
    min_connections = null
    monitor_port    = null
    name            = null
    port            = null
    weight          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "algorithm" {
  description = "(required) - Balancing method for the service. One of 'ip-hash', 'round-robin', 'uri', 'leastconn', 'url', or 'httpheader'"
  type        = string
}

variable "algorithm_parameters" {
  description = "(optional) - Additional options for load balancing algorithm for httpheader or url algorithms"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Server pool description"
  type        = string
  default     = null
}

variable "edge_gateway" {
  description = "(required) - Edge gateway name in which the LB Server Pool is located"
  type        = string
}

variable "enable_transparency" {
  description = "(optional) - Makes client IP addresses visible to the backend servers"
  type        = bool
  default     = null
}

variable "monitor_id" {
  description = "(optional) - Load Balancer Service Monitor ID"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Unique LB Server Pool name"
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

variable "member" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      condition       = string
      id              = string
      ip_address      = string
      max_connections = number
      min_connections = number
      monitor_port    = number
      name            = string
      port            = number
      weight          = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vcd_lb_server_pool" "this" {
  # algorithm - (required) is a type of string
  algorithm = var.algorithm
  # algorithm_parameters - (optional) is a type of string
  algorithm_parameters = var.algorithm_parameters
  # description - (optional) is a type of string
  description = var.description
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # enable_transparency - (optional) is a type of bool
  enable_transparency = var.enable_transparency
  # monitor_id - (optional) is a type of string
  monitor_id = var.monitor_id
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "member" {
    for_each = var.member
    content {
      # condition - (required) is a type of string
      condition = member.value["condition"]
      # ip_address - (required) is a type of string
      ip_address = member.value["ip_address"]
      # max_connections - (optional) is a type of number
      max_connections = member.value["max_connections"]
      # min_connections - (optional) is a type of number
      min_connections = member.value["min_connections"]
      # monitor_port - (required) is a type of number
      monitor_port = member.value["monitor_port"]
      # name - (required) is a type of string
      name = member.value["name"]
      # port - (required) is a type of number
      port = member.value["port"]
      # weight - (required) is a type of number
      weight = member.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_lb_server_pool.this.id
}

output "this" {
  value = vcd_lb_server_pool.this
}
```

[top](#index)