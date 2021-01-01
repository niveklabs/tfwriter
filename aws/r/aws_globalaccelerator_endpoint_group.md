# aws_globalaccelerator_endpoint_group
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)
### Terraform
```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```
[top](#index)
### Example Usage
```hcl
module "aws_globalaccelerator_endpoint_group" {
  source = "./modules/aws/r/aws_globalaccelerator_endpoint_group"

  # endpoint_group_region - (optional) is a type of string
  endpoint_group_region = null
  # health_check_interval_seconds - (optional) is a type of number
  health_check_interval_seconds = null
  # health_check_path - (optional) is a type of string
  health_check_path = null
  # health_check_port - (optional) is a type of number
  health_check_port = null
  # health_check_protocol - (optional) is a type of string
  health_check_protocol = null
  # listener_arn - (required) is a type of string
  listener_arn = null
  # threshold_count - (optional) is a type of number
  threshold_count = null
  # traffic_dial_percentage - (optional) is a type of number
  traffic_dial_percentage = null

  endpoint_configuration = [{
    client_ip_preservation_enabled = null
    endpoint_id                    = null
    weight                         = null
  }]

  port_override = [{
    endpoint_port = null
    listener_port = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "endpoint_group_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_interval_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "listener_arn" {
  description = "(required)"
  type        = string
}

variable "threshold_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "traffic_dial_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "endpoint_configuration" {
  description = "nested mode: NestingSet, min items: 0, max items: 10"
  type = set(object(
    {
      client_ip_preservation_enabled = bool
      endpoint_id                    = string
      weight                         = number
    }
  ))
  default = []
}

variable "port_override" {
  description = "nested mode: NestingSet, min items: 0, max items: 10"
  type = set(object(
    {
      endpoint_port = number
      listener_port = number
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_globalaccelerator_endpoint_group" "this" {
  endpoint_group_region         = var.endpoint_group_region
  health_check_interval_seconds = var.health_check_interval_seconds
  health_check_path             = var.health_check_path
  health_check_port             = var.health_check_port
  health_check_protocol         = var.health_check_protocol
  listener_arn                  = var.listener_arn
  threshold_count               = var.threshold_count
  traffic_dial_percentage       = var.traffic_dial_percentage

  dynamic "endpoint_configuration" {
    for_each = var.endpoint_configuration
    content {
      client_ip_preservation_enabled = endpoint_configuration.value["client_ip_preservation_enabled"]
      endpoint_id                    = endpoint_configuration.value["endpoint_id"]
      weight                         = endpoint_configuration.value["weight"]
    }
  }

  dynamic "port_override" {
    for_each = var.port_override
    content {
      endpoint_port = port_override.value["endpoint_port"]
      listener_port = port_override.value["listener_port"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_globalaccelerator_endpoint_group.this.arn
}

output "endpoint_group_region" {
  description = "returns a string"
  value       = aws_globalaccelerator_endpoint_group.this.endpoint_group_region
}

output "health_check_path" {
  description = "returns a string"
  value       = aws_globalaccelerator_endpoint_group.this.health_check_path
}

output "health_check_port" {
  description = "returns a number"
  value       = aws_globalaccelerator_endpoint_group.this.health_check_port
}

output "id" {
  description = "returns a string"
  value       = aws_globalaccelerator_endpoint_group.this.id
}

output "this" {
  value = aws_globalaccelerator_endpoint_group.this
}
```
[top](#index)
