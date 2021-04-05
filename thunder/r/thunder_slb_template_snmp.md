# thunder_slb_template_snmp

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
module "thunder_slb_template_snmp" {
  source = "./modules/thunder/r/thunder_slb_template_snmp"

  # auth_key - (optional) is a type of string
  auth_key = null
  # auth_proto - (optional) is a type of string
  auth_proto = null
  # community - (optional) is a type of string
  community = null
  # context_engine_id - (optional) is a type of string
  context_engine_id = null
  # context_name - (optional) is a type of string
  context_name = null
  # host - (optional) is a type of string
  host = null
  # interface - (optional) is a type of number
  interface = null
  # interval - (optional) is a type of number
  interval = null
  # oid - (optional) is a type of string
  oid = null
  # port - (optional) is a type of number
  port = null
  # priv_key - (optional) is a type of string
  priv_key = null
  # priv_proto - (optional) is a type of string
  priv_proto = null
  # security_engine_id - (optional) is a type of string
  security_engine_id = null
  # security_level - (optional) is a type of string
  security_level = null
  # snmp_name - (optional) is a type of string
  snmp_name = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # username - (optional) is a type of string
  username = null
  # uuid - (optional) is a type of string
  uuid = null
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_proto" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "community" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "context_engine_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "context_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "oid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "priv_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priv_proto" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_engine_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snmp_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_snmp" "this" {
  auth_key           = var.auth_key
  auth_proto         = var.auth_proto
  community          = var.community
  context_engine_id  = var.context_engine_id
  context_name       = var.context_name
  host               = var.host
  interface          = var.interface
  interval           = var.interval
  oid                = var.oid
  port               = var.port
  priv_key           = var.priv_key
  priv_proto         = var.priv_proto
  security_engine_id = var.security_engine_id
  security_level     = var.security_level
  snmp_name          = var.snmp_name
  user_tag           = var.user_tag
  username           = var.username
  uuid               = var.uuid
  version            = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_snmp.this.id
}

output "this" {
  value = thunder_slb_template_snmp.this
}
```

[top](#index)