# thunder_slb_template_mqtt

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
module "thunder_slb_template_mqtt" {
  source = "./modules/thunder/r/thunder_slb_template_mqtt"

  # clientid_hash_first - (optional) is a type of number
  clientid_hash_first = null
  # clientid_hash_last - (optional) is a type of number
  clientid_hash_last = null
  # clientid_hash_offset - (optional) is a type of number
  clientid_hash_offset = null
  # clientid_hash_persist - (optional) is a type of number
  clientid_hash_persist = null
  # name - (optional) is a type of string
  name = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "clientid_hash_first" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "clientid_hash_last" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "clientid_hash_offset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "clientid_hash_persist" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
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
resource "thunder_slb_template_mqtt" "this" {
  clientid_hash_first   = var.clientid_hash_first
  clientid_hash_last    = var.clientid_hash_last
  clientid_hash_offset  = var.clientid_hash_offset
  clientid_hash_persist = var.clientid_hash_persist
  name                  = var.name
  user_tag              = var.user_tag
  uuid                  = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_mqtt.this.id
}

output "this" {
  value = thunder_slb_template_mqtt.this
}
```

[top](#index)