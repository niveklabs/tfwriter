# ecl_security_host_based_v1

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_security_host_based_v1" {
  source = "./modules/ecl/r/ecl_security_host_based_v1"

  # dsm_lang - (required) is a type of string
  dsm_lang = null
  # locale - (optional) is a type of string
  locale = null
  # mail_address - (required) is a type of string
  mail_address = null
  # max_agent_value - (required) is a type of number
  max_agent_value = null
  # service_order_service - (required) is a type of string
  service_order_service = null
  # tenant_id - (required) is a type of string
  tenant_id = null
  # time_zone - (required) is a type of string
  time_zone = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dsm_lang" {
  description = "(required)"
  type        = string
}

variable "locale" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mail_address" {
  description = "(required)"
  type        = string
}

variable "max_agent_value" {
  description = "(required)"
  type        = number
}

variable "service_order_service" {
  description = "(required)"
  type        = string
}

variable "tenant_id" {
  description = "(required)"
  type        = string
}

variable "time_zone" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_security_host_based_v1" "this" {
  dsm_lang              = var.dsm_lang
  locale                = var.locale
  mail_address          = var.mail_address
  max_agent_value       = var.max_agent_value
  service_order_service = var.service_order_service
  tenant_id             = var.tenant_id
  time_zone             = var.time_zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ecl_security_host_based_v1.this.id
}

output "this" {
  value = ecl_security_host_based_v1.this
}
```

[top](#index)