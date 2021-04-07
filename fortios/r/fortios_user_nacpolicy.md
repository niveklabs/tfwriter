# fortios_user_nacpolicy

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
module "fortios_user_nacpolicy" {
  source = "./modules/fortios/r/fortios_user_nacpolicy"

  # category - (optional) is a type of string
  category = null
  # description - (optional) is a type of string
  description = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # ems_tag - (optional) is a type of string
  ems_tag = null
  # family - (optional) is a type of string
  family = null
  # host - (optional) is a type of string
  host = null
  # hw_vendor - (optional) is a type of string
  hw_vendor = null
  # hw_version - (optional) is a type of string
  hw_version = null
  # mac - (optional) is a type of string
  mac = null
  # name - (optional) is a type of string
  name = null
  # os - (optional) is a type of string
  os = null
  # src - (optional) is a type of string
  src = null
  # status - (optional) is a type of string
  status = null
  # sw_version - (optional) is a type of string
  sw_version = null
  # switch_auto_auth - (optional) is a type of string
  switch_auto_auth = null
  # switch_fortilink - (optional) is a type of string
  switch_fortilink = null
  # switch_mac_policy - (optional) is a type of string
  switch_mac_policy = null
  # switch_port_policy - (optional) is a type of string
  switch_port_policy = null
  # type - (optional) is a type of string
  type = null
  # user - (optional) is a type of string
  user = null
  # user_group - (optional) is a type of string
  user_group = null

  switch_scope = [{
    switch_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ems_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "family" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hw_vendor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hw_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "src" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sw_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switch_auto_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switch_fortilink" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switch_mac_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switch_port_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switch_scope" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      switch_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_nacpolicy" "this" {
  # category - (optional) is a type of string
  category = var.category
  # description - (optional) is a type of string
  description = var.description
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # ems_tag - (optional) is a type of string
  ems_tag = var.ems_tag
  # family - (optional) is a type of string
  family = var.family
  # host - (optional) is a type of string
  host = var.host
  # hw_vendor - (optional) is a type of string
  hw_vendor = var.hw_vendor
  # hw_version - (optional) is a type of string
  hw_version = var.hw_version
  # mac - (optional) is a type of string
  mac = var.mac
  # name - (optional) is a type of string
  name = var.name
  # os - (optional) is a type of string
  os = var.os
  # src - (optional) is a type of string
  src = var.src
  # status - (optional) is a type of string
  status = var.status
  # sw_version - (optional) is a type of string
  sw_version = var.sw_version
  # switch_auto_auth - (optional) is a type of string
  switch_auto_auth = var.switch_auto_auth
  # switch_fortilink - (optional) is a type of string
  switch_fortilink = var.switch_fortilink
  # switch_mac_policy - (optional) is a type of string
  switch_mac_policy = var.switch_mac_policy
  # switch_port_policy - (optional) is a type of string
  switch_port_policy = var.switch_port_policy
  # type - (optional) is a type of string
  type = var.type
  # user - (optional) is a type of string
  user = var.user
  # user_group - (optional) is a type of string
  user_group = var.user_group

  dynamic "switch_scope" {
    for_each = var.switch_scope
    content {
      # switch_id - (optional) is a type of string
      switch_id = switch_scope.value["switch_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "category" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.category
}

output "description" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.description
}

output "ems_tag" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.ems_tag
}

output "family" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.family
}

output "host" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.host
}

output "hw_vendor" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.hw_vendor
}

output "hw_version" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.hw_version
}

output "id" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.id
}

output "mac" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.mac
}

output "name" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.name
}

output "os" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.os
}

output "src" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.src
}

output "status" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.status
}

output "sw_version" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.sw_version
}

output "switch_auto_auth" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.switch_auto_auth
}

output "switch_fortilink" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.switch_fortilink
}

output "switch_mac_policy" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.switch_mac_policy
}

output "switch_port_policy" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.switch_port_policy
}

output "type" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.type
}

output "user" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.user
}

output "user_group" {
  description = "returns a string"
  value       = fortios_user_nacpolicy.this.user_group
}

output "this" {
  value = fortios_user_nacpolicy.this
}
```

[top](#index)