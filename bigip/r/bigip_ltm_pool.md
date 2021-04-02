# bigip_ltm_pool

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_pool" {
  source = "./modules/bigip/r/bigip_ltm_pool"

  # allow_nat - (optional) is a type of string
  allow_nat = null
  # allow_snat - (optional) is a type of string
  allow_snat = null
  # description - (optional) is a type of string
  description = null
  # load_balancing_mode - (optional) is a type of string
  load_balancing_mode = null
  # minimum_active_members - (optional) is a type of number
  minimum_active_members = null
  # monitors - (optional) is a type of set of string
  monitors = []
  # name - (required) is a type of string
  name = null
  # reselect_tries - (optional) is a type of number
  reselect_tries = null
  # service_down_action - (optional) is a type of string
  service_down_action = null
  # slow_ramp_time - (optional) is a type of number
  slow_ramp_time = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_nat" {
  description = "(optional) - Specifies whether NATs are automatically enabled or disabled for any connections using this pool."
  type        = string
  default     = null
}

variable "allow_snat" {
  description = "(optional) - Specifies whether SNATs are automatically enabled or disabled for any connections using this pool."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Specifies descriptive text that identifies the pool."
  type        = string
  default     = null
}

variable "load_balancing_mode" {
  description = "(optional) - Specifies the load balancing method. The default is Round Robin.Possible values: round-robin, ..."
  type        = string
  default     = null
}

variable "minimum_active_members" {
  description = "(optional) - Specifies whether the system load balances traffic according to the priority number assigned to the pool member,Default Value is 0(disabled)"
  type        = number
  default     = null
}

variable "monitors" {
  description = "(optional) - Specifies an association between a health or performance monitor and an entire pool, rather than with individual pool members"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the pool"
  type        = string
}

variable "reselect_tries" {
  description = "(optional) - Specifies the number of times the system tries to contact a new pool member after a passive failure."
  type        = number
  default     = null
}

variable "service_down_action" {
  description = "(optional) - Specifies how the system should respond when the target pool member becomes unavailable. The default is None, Possible values: [none, reset, reselect, drop]"
  type        = string
  default     = null
}

variable "slow_ramp_time" {
  description = "(optional) - Specifies the duration during which the system sends less traffic to a newly-enabled pool member."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_pool" "this" {
  allow_nat              = var.allow_nat
  allow_snat             = var.allow_snat
  description            = var.description
  load_balancing_mode    = var.load_balancing_mode
  minimum_active_members = var.minimum_active_members
  monitors               = var.monitors
  name                   = var.name
  reselect_tries         = var.reselect_tries
  service_down_action    = var.service_down_action
  slow_ramp_time         = var.slow_ramp_time
}
```

[top](#index)

### Outputs

```terraform
output "allow_nat" {
  description = "returns a string"
  value       = bigip_ltm_pool.this.allow_nat
}

output "allow_snat" {
  description = "returns a string"
  value       = bigip_ltm_pool.this.allow_snat
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_pool.this.id
}

output "load_balancing_mode" {
  description = "returns a string"
  value       = bigip_ltm_pool.this.load_balancing_mode
}

output "minimum_active_members" {
  description = "returns a number"
  value       = bigip_ltm_pool.this.minimum_active_members
}

output "monitors" {
  description = "returns a set of string"
  value       = bigip_ltm_pool.this.monitors
}

output "reselect_tries" {
  description = "returns a number"
  value       = bigip_ltm_pool.this.reselect_tries
}

output "service_down_action" {
  description = "returns a string"
  value       = bigip_ltm_pool.this.service_down_action
}

output "slow_ramp_time" {
  description = "returns a number"
  value       = bigip_ltm_pool.this.slow_ramp_time
}

output "this" {
  value = bigip_ltm_pool.this
}
```

[top](#index)