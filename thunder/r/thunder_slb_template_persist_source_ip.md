# thunder_slb_template_persist_source_ip

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_template_persist_source_ip" {
  source = "./modules/thunder/r/thunder_slb_template_persist_source_ip"

  # dont_honor_conn_rules - (optional) is a type of number
  dont_honor_conn_rules = null
  # enforce_higher_priority - (optional) is a type of number
  enforce_higher_priority = null
  # hash_persist - (optional) is a type of number
  hash_persist = null
  # incl_dst_ip - (optional) is a type of number
  incl_dst_ip = null
  # incl_sport - (optional) is a type of number
  incl_sport = null
  # match_type - (optional) is a type of number
  match_type = null
  # name - (optional) is a type of string
  name = null
  # netmask - (optional) is a type of string
  netmask = null
  # netmask6 - (optional) is a type of number
  netmask6 = null
  # primary_port - (optional) is a type of number
  primary_port = null
  # scan_all_members - (optional) is a type of number
  scan_all_members = null
  # server - (optional) is a type of number
  server = null
  # service_group - (optional) is a type of number
  service_group = null
  # timeout - (optional) is a type of number
  timeout = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "dont_honor_conn_rules" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enforce_higher_priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hash_persist" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "incl_dst_ip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "incl_sport" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "match_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "netmask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "netmask6" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "primary_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "scan_all_members" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_group" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_persist_source_ip" "this" {
  # dont_honor_conn_rules - (optional) is a type of number
  dont_honor_conn_rules = var.dont_honor_conn_rules
  # enforce_higher_priority - (optional) is a type of number
  enforce_higher_priority = var.enforce_higher_priority
  # hash_persist - (optional) is a type of number
  hash_persist = var.hash_persist
  # incl_dst_ip - (optional) is a type of number
  incl_dst_ip = var.incl_dst_ip
  # incl_sport - (optional) is a type of number
  incl_sport = var.incl_sport
  # match_type - (optional) is a type of number
  match_type = var.match_type
  # name - (optional) is a type of string
  name = var.name
  # netmask - (optional) is a type of string
  netmask = var.netmask
  # netmask6 - (optional) is a type of number
  netmask6 = var.netmask6
  # primary_port - (optional) is a type of number
  primary_port = var.primary_port
  # scan_all_members - (optional) is a type of number
  scan_all_members = var.scan_all_members
  # server - (optional) is a type of number
  server = var.server
  # service_group - (optional) is a type of number
  service_group = var.service_group
  # timeout - (optional) is a type of number
  timeout = var.timeout
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_persist_source_ip.this.id
}

output "this" {
  value = thunder_slb_template_persist_source_ip.this
}
```

[top](#index)