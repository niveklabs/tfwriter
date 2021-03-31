# opc_lbaas_server_pool

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_lbaas_server_pool" {
  source = "./modules/opc/r/opc_lbaas_server_pool"

  # enabled - (optional) is a type of bool
  enabled = null
  # load_balancer - (required) is a type of string
  load_balancer = null
  # name - (required) is a type of string
  name = null
  # servers - (required) is a type of set of string
  servers = []
  # tags - (optional) is a type of set of string
  tags = []
  # vnic_set - (optional) is a type of string
  vnic_set = null

  health_check = [{
    accepted_return_codes = []
    enabled               = null
    healthy_threshold     = null
    interval              = null
    path                  = null
    timeout               = null
    type                  = null
    unhealthy_threshold   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "load_balancer" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "servers" {
  description = "(required)"
  type        = set(string)
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "vnic_set" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      accepted_return_codes = list(string)
      enabled               = bool
      healthy_threshold     = number
      interval              = number
      path                  = string
      timeout               = number
      type                  = string
      unhealthy_threshold   = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opc_lbaas_server_pool" "this" {
  enabled       = var.enabled
  load_balancer = var.load_balancer
  name          = var.name
  servers       = var.servers
  tags          = var.tags
  vnic_set      = var.vnic_set

  dynamic "health_check" {
    for_each = var.health_check
    content {
      accepted_return_codes = health_check.value["accepted_return_codes"]
      enabled               = health_check.value["enabled"]
      healthy_threshold     = health_check.value["healthy_threshold"]
      interval              = health_check.value["interval"]
      path                  = health_check.value["path"]
      timeout               = health_check.value["timeout"]
      type                  = health_check.value["type"]
      unhealthy_threshold   = health_check.value["unhealthy_threshold"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "consumers" {
  description = "returns a string"
  value       = opc_lbaas_server_pool.this.consumers
}

output "id" {
  description = "returns a string"
  value       = opc_lbaas_server_pool.this.id
}

output "operation_details" {
  description = "returns a bool"
  value       = opc_lbaas_server_pool.this.operation_details
}

output "state" {
  description = "returns a string"
  value       = opc_lbaas_server_pool.this.state
}

output "status" {
  description = "returns a bool"
  value       = opc_lbaas_server_pool.this.status
}

output "uri" {
  description = "returns a string"
  value       = opc_lbaas_server_pool.this.uri
}

output "this" {
  value = opc_lbaas_server_pool.this
}
```

[top](#index)