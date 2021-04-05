# thunder_fw_global

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
module "thunder_fw_global" {
  source = "./modules/thunder/r/thunder_fw_global"

  # alg_processing - (optional) is a type of string
  alg_processing = null
  # disable_ip_fw_sessions - (optional) is a type of number
  disable_ip_fw_sessions = null
  # extended_matching - (optional) is a type of string
  extended_matching = null
  # listen_on_port_timeout - (optional) is a type of number
  listen_on_port_timeout = null
  # natip_ddos_protection - (optional) is a type of string
  natip_ddos_protection = null
  # permit_default_action - (optional) is a type of string
  permit_default_action = null
  # respond_to_user_mac - (optional) is a type of number
  respond_to_user_mac = null
  # uuid - (optional) is a type of string
  uuid = null

  disable_app_list = [{
    disable_application_category = null
    disable_application_protocol = null
  }]

  sampling_enable = [{
    counters1 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alg_processing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_ip_fw_sessions" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "extended_matching" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "listen_on_port_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "natip_ddos_protection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "permit_default_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "respond_to_user_mac" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_app_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      disable_application_category = string
      disable_application_protocol = string
    }
  ))
  default = []
}

variable "sampling_enable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      counters1 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_fw_global" "this" {
  alg_processing         = var.alg_processing
  disable_ip_fw_sessions = var.disable_ip_fw_sessions
  extended_matching      = var.extended_matching
  listen_on_port_timeout = var.listen_on_port_timeout
  natip_ddos_protection  = var.natip_ddos_protection
  permit_default_action  = var.permit_default_action
  respond_to_user_mac    = var.respond_to_user_mac
  uuid                   = var.uuid

  dynamic "disable_app_list" {
    for_each = var.disable_app_list
    content {
      disable_application_category = disable_app_list.value["disable_application_category"]
      disable_application_protocol = disable_app_list.value["disable_application_protocol"]
    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      counters1 = sampling_enable.value["counters1"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_global.this.id
}

output "this" {
  value = thunder_fw_global.this
}
```

[top](#index)