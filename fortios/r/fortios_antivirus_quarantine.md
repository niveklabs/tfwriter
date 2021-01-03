# fortios_antivirus_quarantine

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_antivirus_quarantine" {
  source = "./modules/fortios/r/fortios_antivirus_quarantine"

  # agelimit - (optional) is a type of number
  agelimit = null
  # destination - (optional) is a type of string
  destination = null
  # drop_blocked - (optional) is a type of string
  drop_blocked = null
  # drop_heuristic - (optional) is a type of string
  drop_heuristic = null
  # drop_infected - (optional) is a type of string
  drop_infected = null
  # lowspace - (optional) is a type of string
  lowspace = null
  # maxfilesize - (optional) is a type of number
  maxfilesize = null
  # quarantine_quota - (optional) is a type of number
  quarantine_quota = null
  # store_blocked - (optional) is a type of string
  store_blocked = null
  # store_heuristic - (optional) is a type of string
  store_heuristic = null
  # store_infected - (optional) is a type of string
  store_infected = null
}
```

[top](#index)

### Variables

```terraform
variable "agelimit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "destination" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "drop_blocked" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "drop_heuristic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "drop_infected" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lowspace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maxfilesize" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "quarantine_quota" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "store_blocked" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "store_heuristic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "store_infected" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_antivirus_quarantine" "this" {
  agelimit         = var.agelimit
  destination      = var.destination
  drop_blocked     = var.drop_blocked
  drop_heuristic   = var.drop_heuristic
  drop_infected    = var.drop_infected
  lowspace         = var.lowspace
  maxfilesize      = var.maxfilesize
  quarantine_quota = var.quarantine_quota
  store_blocked    = var.store_blocked
  store_heuristic  = var.store_heuristic
  store_infected   = var.store_infected
}
```

[top](#index)

### Outputs

```terraform
output "agelimit" {
  description = "returns a number"
  value       = fortios_antivirus_quarantine.this.agelimit
}

output "destination" {
  description = "returns a string"
  value       = fortios_antivirus_quarantine.this.destination
}

output "drop_blocked" {
  description = "returns a string"
  value       = fortios_antivirus_quarantine.this.drop_blocked
}

output "drop_heuristic" {
  description = "returns a string"
  value       = fortios_antivirus_quarantine.this.drop_heuristic
}

output "drop_infected" {
  description = "returns a string"
  value       = fortios_antivirus_quarantine.this.drop_infected
}

output "id" {
  description = "returns a string"
  value       = fortios_antivirus_quarantine.this.id
}

output "lowspace" {
  description = "returns a string"
  value       = fortios_antivirus_quarantine.this.lowspace
}

output "maxfilesize" {
  description = "returns a number"
  value       = fortios_antivirus_quarantine.this.maxfilesize
}

output "quarantine_quota" {
  description = "returns a number"
  value       = fortios_antivirus_quarantine.this.quarantine_quota
}

output "store_blocked" {
  description = "returns a string"
  value       = fortios_antivirus_quarantine.this.store_blocked
}

output "store_heuristic" {
  description = "returns a string"
  value       = fortios_antivirus_quarantine.this.store_heuristic
}

output "store_infected" {
  description = "returns a string"
  value       = fortios_antivirus_quarantine.this.store_infected
}

output "this" {
  value = fortios_antivirus_quarantine.this
}
```

[top](#index)