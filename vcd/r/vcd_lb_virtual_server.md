# vcd_lb_virtual_server

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
module "vcd_lb_virtual_server" {
  source = "./modules/vcd/r/vcd_lb_virtual_server"

  # app_profile_id - (optional) is a type of string
  app_profile_id = null
  # app_rule_ids - (optional) is a type of list of string
  app_rule_ids = []
  # connection_limit - (optional) is a type of number
  connection_limit = null
  # connection_rate_limit - (optional) is a type of number
  connection_rate_limit = null
  # description - (optional) is a type of string
  description = null
  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # enable_acceleration - (optional) is a type of bool
  enable_acceleration = null
  # enabled - (optional) is a type of bool
  enabled = null
  # ip_address - (required) is a type of string
  ip_address = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # port - (required) is a type of number
  port = null
  # protocol - (required) is a type of string
  protocol = null
  # server_pool_id - (optional) is a type of string
  server_pool_id = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "app_profile_id" {
  description = "(optional) - Application profile ID to be associated with the virtual server"
  type        = string
  default     = null
}

variable "app_rule_ids" {
  description = "(optional) - List of attached application rule IDs"
  type        = list(string)
  default     = null
}

variable "connection_limit" {
  description = "(optional) - Maximum concurrent connections that the virtual server can process"
  type        = number
  default     = null
}

variable "connection_rate_limit" {
  description = "(optional) - Maximum incoming new connection requests per second"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - Virtual Server description"
  type        = string
  default     = null
}

variable "edge_gateway" {
  description = "(required) - Edge gateway name in which the LB Virtual Server is located"
  type        = string
}

variable "enable_acceleration" {
  description = "(optional) - Enable virtual server acceleration"
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional) - Defines if the virtual server is enabled"
  type        = bool
  default     = null
}

variable "ip_address" {
  description = "(required) - IP address that the load balancer listens on"
  type        = string
}

variable "name" {
  description = "(required) - Unique Virtual Server name"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "port" {
  description = "(required) - Port number that the load balancer listens on"
  type        = number
}

variable "protocol" {
  description = "(required) - Protocol that the virtual server accepts"
  type        = string
}

variable "server_pool_id" {
  description = "(optional) - The server pool that the load balancer will use"
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

### Resource

```terraform
resource "vcd_lb_virtual_server" "this" {
  # app_profile_id - (optional) is a type of string
  app_profile_id = var.app_profile_id
  # app_rule_ids - (optional) is a type of list of string
  app_rule_ids = var.app_rule_ids
  # connection_limit - (optional) is a type of number
  connection_limit = var.connection_limit
  # connection_rate_limit - (optional) is a type of number
  connection_rate_limit = var.connection_rate_limit
  # description - (optional) is a type of string
  description = var.description
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # enable_acceleration - (optional) is a type of bool
  enable_acceleration = var.enable_acceleration
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # ip_address - (required) is a type of string
  ip_address = var.ip_address
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # port - (required) is a type of number
  port = var.port
  # protocol - (required) is a type of string
  protocol = var.protocol
  # server_pool_id - (optional) is a type of string
  server_pool_id = var.server_pool_id
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_lb_virtual_server.this.id
}

output "this" {
  value = vcd_lb_virtual_server.this
}
```

[top](#index)