# thunder_slb_ssl_expire_check

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
module "thunder_slb_ssl_expire_check" {
  source = "./modules/thunder/r/thunder_slb_ssl_expire_check"

  # before - (optional) is a type of number
  before = null
  # expire_address1 - (optional) is a type of string
  expire_address1 = null
  # interval_days - (optional) is a type of number
  interval_days = null
  # ssl_expire_email_address - (optional) is a type of string
  ssl_expire_email_address = null
  # uuid - (optional) is a type of string
  uuid = null

  exception = [{
    action           = null
    certificate_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "before" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "expire_address1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interval_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_expire_email_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exception" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      action           = string
      certificate_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_ssl_expire_check" "this" {
  before                   = var.before
  expire_address1          = var.expire_address1
  interval_days            = var.interval_days
  ssl_expire_email_address = var.ssl_expire_email_address
  uuid                     = var.uuid

  dynamic "exception" {
    for_each = var.exception
    content {
      action           = exception.value["action"]
      certificate_name = exception.value["certificate_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_ssl_expire_check.this.id
}

output "this" {
  value = thunder_slb_ssl_expire_check.this
}
```

[top](#index)