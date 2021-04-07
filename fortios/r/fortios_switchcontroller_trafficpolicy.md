# fortios_switchcontroller_trafficpolicy

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "fortios_switchcontroller_trafficpolicy" {
  source = "./modules/fortios/r/fortios_switchcontroller_trafficpolicy"

  # cos - (optional) is a type of number
  cos = null
  # cos_queue - (optional) is a type of number
  cos_queue = null
  # description - (optional) is a type of string
  description = null
  # fosid - (optional) is a type of number
  fosid = null
  # guaranteed_bandwidth - (optional) is a type of number
  guaranteed_bandwidth = null
  # guaranteed_burst - (optional) is a type of number
  guaranteed_burst = null
  # maximum_burst - (optional) is a type of number
  maximum_burst = null
  # name - (required) is a type of string
  name = null
  # policer_status - (optional) is a type of string
  policer_status = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "cos" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cos_queue" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "guaranteed_bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "guaranteed_burst" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_burst" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policer_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_trafficpolicy" "this" {
  # cos - (optional) is a type of number
  cos = var.cos
  # cos_queue - (optional) is a type of number
  cos_queue = var.cos_queue
  # description - (optional) is a type of string
  description = var.description
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # guaranteed_bandwidth - (optional) is a type of number
  guaranteed_bandwidth = var.guaranteed_bandwidth
  # guaranteed_burst - (optional) is a type of number
  guaranteed_burst = var.guaranteed_burst
  # maximum_burst - (optional) is a type of number
  maximum_burst = var.maximum_burst
  # name - (required) is a type of string
  name = var.name
  # policer_status - (optional) is a type of string
  policer_status = var.policer_status
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "cos" {
  description = "returns a number"
  value       = fortios_switchcontroller_trafficpolicy.this.cos
}

output "cos_queue" {
  description = "returns a number"
  value       = fortios_switchcontroller_trafficpolicy.this.cos_queue
}

output "description" {
  description = "returns a string"
  value       = fortios_switchcontroller_trafficpolicy.this.description
}

output "fosid" {
  description = "returns a number"
  value       = fortios_switchcontroller_trafficpolicy.this.fosid
}

output "guaranteed_bandwidth" {
  description = "returns a number"
  value       = fortios_switchcontroller_trafficpolicy.this.guaranteed_bandwidth
}

output "guaranteed_burst" {
  description = "returns a number"
  value       = fortios_switchcontroller_trafficpolicy.this.guaranteed_burst
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_trafficpolicy.this.id
}

output "maximum_burst" {
  description = "returns a number"
  value       = fortios_switchcontroller_trafficpolicy.this.maximum_burst
}

output "policer_status" {
  description = "returns a string"
  value       = fortios_switchcontroller_trafficpolicy.this.policer_status
}

output "type" {
  description = "returns a string"
  value       = fortios_switchcontroller_trafficpolicy.this.type
}

output "this" {
  value = fortios_switchcontroller_trafficpolicy.this
}
```

[top](#index)